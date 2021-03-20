---
title: Beleid voor veilige bijlagen instellen in Microsoft Defender voor Office 365
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
description: Meer informatie over het definiëren van beleidsregels voor veilige bijlagen om uw organisatie te beschermen tegen schadelijke bestanden in e-mail.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d48e373dc95aaa65d0f436f99208d926477aacd6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918712"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ac265-103">Beleid voor veilige bijlagen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ac265-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ac265-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ac265-104">**Applies to**</span></span>
- [<span data-ttu-id="ac265-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ac265-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ac265-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac265-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="ac265-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="ac265-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="ac265-108">Als u een thuisgebruiker bent die informatie zoekt over het scannen van bijlagen in Outlook, gaat u naar [Geavanceerde Outlook.com beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="ac265-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="ac265-109">Veilige bijlagen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) die een virtuele omgeving gebruikt om bijlagen in binnenkomende e-mailberichten te controleren nadat ze zijn gescand door [anti-malwarebeveiliging in Exchange Online Protection (EOP),](anti-malware-protection.md)maar vóór de bezorging aan geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="ac265-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="ac265-110">Zie Veilige bijlagen [in Microsoft Defender voor Office 365](atp-safe-attachments.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ac265-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="ac265-111">Er is geen ingebouwd of standaardbeleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ac265-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="ac265-112">Als u veilige bijlagen wilt laten scannen van e-mailberichtbijlagen, moet u een of meer beleidsregels voor veilige bijlagen maken, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ac265-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="ac265-113">U kunt beleidsregels voor veilige bijlagen configureren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="ac265-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="ac265-114">De basiselementen van een beleid voor veilige bijlagen zijn:</span><span class="sxs-lookup"><span data-stu-id="ac265-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="ac265-115">**Het beleid** voor veilige bijlagen: geeft de acties voor onbekende malwaredetecties op, of berichten met malwarebijlagen naar een opgegeven e-mailadres moeten worden verzonden en of berichten moeten worden verzonden als het scannen van veilige bijlagen niet kan worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="ac265-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="ac265-116">**De veilige bijlageregel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="ac265-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="ac265-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u veilige bijlagen beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="ac265-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ac265-118">Wanneer u een beleid voor veilige bijlagen maakt, maakt u tegelijkertijd een veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="ac265-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ac265-119">Wanneer u een beleid voor veilige bijlagen wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de regel voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ac265-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="ac265-120">Alle andere instellingen wijzigen het bijbehorende beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ac265-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="ac265-121">Wanneer u een beleid voor veilige bijlagen verwijdert, worden de veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ac265-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="ac265-122">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="ac265-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ac265-123">Zie de sectie Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) gebruiken voor het configureren van beleidsregels voor veilige bijlagen verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ac265-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="ac265-124">In het gebied met algemene instellingen van instellingen voor veilige bijlagen configureert u functies die niet afhankelijk zijn van beleidsregels voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ac265-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="ac265-125">Zie Veilige bijlagen [in microsoft](turn-on-atp-for-spo-odb-and-teams.md) 365 E5 in microsoft 365 E5 in microsoft [365 voor instructies.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="ac265-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ac265-126">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ac265-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ac265-127">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ac265-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ac265-128">Als u rechtstreeks naar de pagina **Veilige bijlagen** wilt gaan, gebruikt u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ac265-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ac265-129">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac265-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ac265-130">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac265-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ac265-131">U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="ac265-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ac265-132">Als u beleidsregels voor veilige bijlagen wilt maken, wijzigen  en verwijderen, moet u lid zijn van  de rollengroepen  Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- & compliancecentrum en lid zijn van de rollengroep Organisatiebeheer in Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="ac265-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="ac265-133">Als u alleen-lezen toegang wilt tot beleidsregels voor  veilige bijlagen, moet u lid zijn van de rollengroepen Globale lezer of Beveiligingslezer in het Beveiligings- & Compliancecentrum. </span><span class="sxs-lookup"><span data-stu-id="ac265-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="ac265-134">Zie Machtigingen [in het Beveiligings-](permissions-in-the-security-and-compliance-center.md) & Compliancecentrum en [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ac265-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ac265-135">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ac265-135">**Notes**:</span></span>

  - <span data-ttu-id="ac265-136">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac265-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ac265-137">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ac265-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ac265-138">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="ac265-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ac265-139">Zie Instellingen voor veilige bijlagen voor onze aanbevolen instellingen voor beleid voor veilige [bijlagen.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="ac265-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="ac265-140">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="ac265-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="ac265-141">Gebruik het Beveiligings- & compliancecentrum om beleidsregels voor veilige bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="ac265-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="ac265-142">Als u een aangepast beleid voor veilige bijlagen maakt in het Beveiligings- & Compliancecentrum, worden de veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="ac265-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ac265-143">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="ac265-144">Klik op **de pagina Veilige bijlagen** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="ac265-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="ac265-145">De **wizard Nieuw beleid voor veilige bijlagen wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="ac265-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="ac265-146">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ac265-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ac265-147">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="ac265-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ac265-148">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="ac265-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ac265-149">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ac265-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ac265-150">Configureer **de** volgende instellingen op de pagina Instellingen die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ac265-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ac265-151">**Safe Attachments unknown malware response**: Select one of the following values:</span><span class="sxs-lookup"><span data-stu-id="ac265-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="ac265-152">**Uit:** Deze waarde wordt meestal niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="ac265-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="ac265-153">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="ac265-153">**Monitor**</span></span>
     - <span data-ttu-id="ac265-154">**Blok:** Dit is de standaardwaarde en de aanbevolen waarde in standaard- en strikt [vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ac265-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="ac265-155">**Vervangen**</span><span class="sxs-lookup"><span data-stu-id="ac265-155">**Replace**</span></span>
     - <span data-ttu-id="ac265-156">**Dynamische bezorging (voorbeeldfunctie)**</span><span class="sxs-lookup"><span data-stu-id="ac265-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="ac265-157">Deze waarden worden uitgelegd in [beleidsinstellingen voor veilige bijlagen.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="ac265-157">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="ac265-158">Verzend de bijlage naar het volgende e-mailadres: Voor de actiewaarden  **Blokkeren,** Controleren of Vervangen **kunt** u Omleiding inschakelen selecteren om berichten te verzenden die malwarebijlagen bevatten naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.  </span><span class="sxs-lookup"><span data-stu-id="ac265-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="ac265-159">De aanbeveling voor standaard- en strikte beleidsinstellingen is om omleiding in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ac265-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="ac265-160">Zie Instellingen voor veilige bijlagen voor [meer informatie.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="ac265-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="ac265-161">Pas de **bovenstaande** selectie toe als er malware wordt gescand op bijlagen of als er een fout optreedt: De actie die is opgegeven door Safe **Attachments unknown malware response** wordt uitgevoerd op berichten, zelfs wanneer het scannen van veilige bijlagen niet kan worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="ac265-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="ac265-162">Als u deze optie hebt geselecteerd, selecteert u altijd **Ingeschakeld omleiden.**</span><span class="sxs-lookup"><span data-stu-id="ac265-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="ac265-163">Anders kunnen berichten verloren gaan.</span><span class="sxs-lookup"><span data-stu-id="ac265-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="ac265-164">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ac265-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ac265-165">Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ac265-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ac265-166">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="ac265-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ac265-167">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ac265-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ac265-168">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ac265-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ac265-169">Klik **op Een voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="ac265-169">Click **Add a condition**.</span></span> <span data-ttu-id="ac265-170">Selecteer in de vervolgkeuzekeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="ac265-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ac265-171">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="ac265-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ac265-172">**De geadresseerde is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="ac265-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ac265-173">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ac265-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="ac265-174">Nadat u de voorwaarde hebt geselecteerd, wordt er een bijbehorende vervolgkeuze weergegeven met een **Van deze vakjes.**</span><span class="sxs-lookup"><span data-stu-id="ac265-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ac265-175">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="ac265-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ac265-176">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="ac265-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ac265-177">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="ac265-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ac265-178">Als u afzonderlijke items wilt verwijderen, klikt **u op Pictogram** Verwijderen verwijderen op de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="ac265-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ac265-179">Als u de hele voorwaarde wilt verwijderen, klikt **u op Pictogram** Verwijderen in de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="ac265-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ac265-180">Als u een extra voorwaarde wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="ac265-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ac265-181">Als u uitzonderingen wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="ac265-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ac265-182">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="ac265-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ac265-183">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ac265-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ac265-184">Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ac265-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ac265-185">U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ac265-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ac265-186">Wanneer u klaar bent, klikt u op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="ac265-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="ac265-187">Het compliancecentrum & beveiliging gebruiken om beleidsregels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="ac265-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="ac265-188">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="ac265-189">Selecteer op **de** pagina Veilige bijlagen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="ac265-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="ac265-190">De beleidsdetails worden weergegeven in een fly-out</span><span class="sxs-lookup"><span data-stu-id="ac265-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="ac265-191">Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ac265-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="ac265-192">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="ac265-193">Selecteer op **de** pagina Veilige bijlagen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="ac265-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="ac265-194">Klik in de beleidsdetails die worden weergegeven op **Beleid bewerken.**</span><span class="sxs-lookup"><span data-stu-id="ac265-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="ac265-195">De beschikbare instellingen in de fly-out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie Het beveiligings- [& compliancecentrum](#use-the-security--compliance-center-to-create-safe-attachments-policies) gebruiken om beleidsregels voor veilige bijlagen te maken.</span><span class="sxs-lookup"><span data-stu-id="ac265-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="ac265-196">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="ac265-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="ac265-197">Beleid voor veilige bijlagen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ac265-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="ac265-198">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="ac265-199">Let op de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="ac265-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ac265-200">De schakelknop naar links verplaatsen</span><span class="sxs-lookup"><span data-stu-id="ac265-200">Move the toggle to the left</span></span> ![Beleid uitschakelen](../../media/scc-toggle-off.png) <span data-ttu-id="ac265-202">om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ac265-202">to disable the policy.</span></span>

   - <span data-ttu-id="ac265-203">De schakelknop naar rechts verplaatsen</span><span class="sxs-lookup"><span data-stu-id="ac265-203">Move the toggle to the right</span></span> ![Beleid in-/uit-](../../media/scc-toggle-on.png) <span data-ttu-id="ac265-205">om het beleid in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ac265-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="ac265-206">De prioriteit van het beleid voor veilige bijlagen instellen</span><span class="sxs-lookup"><span data-stu-id="ac265-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="ac265-207">Het beleid voor veilige bijlagen krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere agenten hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="ac265-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="ac265-208">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="ac265-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ac265-209">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="ac265-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ac265-210">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ac265-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ac265-211">Beleidsregels voor veilige bijlagen worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **waarde** Prioriteit 0).</span><span class="sxs-lookup"><span data-stu-id="ac265-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="ac265-212">**Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het beleid voor veilige bijlagen wijzigen nadat u deze hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ac265-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="ac265-213">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de veilige bijlageregel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="ac265-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ac265-214">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="ac265-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="ac265-215">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="ac265-216">Selecteer op **de** pagina Veilige bijlagen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="ac265-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="ac265-217">Klik in de beleidsdetails die worden weergegeven op de beschikbare prioriteitsknop.</span><span class="sxs-lookup"><span data-stu-id="ac265-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="ac265-218">In het beleid Veilige bijlagen met **prioriteit** **0** is alleen de knop **Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ac265-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ac265-219">Het beleid Veilige bijlagen met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ac265-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ac265-220">Als u drie of meer beleidsregels voor veilige bijlagen hebt,  hebben beleidsregels tussen de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar. </span><span class="sxs-lookup"><span data-stu-id="ac265-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ac265-221">Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ac265-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ac265-222">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ac265-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="ac265-223">Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ac265-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="ac265-224">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="ac265-225">Selecteer op **de** pagina Veilige bijlagen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="ac265-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="ac265-226">Klik in de beleidsdetails die worden weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ac265-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="ac265-227">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om beleidsregels voor veilige bijlagen te configureren</span><span class="sxs-lookup"><span data-stu-id="ac265-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="ac265-228">Zoals eerder beschreven, bestaat een beleid voor veilige bijlagen uit een beleid voor veilige bijlagen en een veilige bijlageregel.</span><span class="sxs-lookup"><span data-stu-id="ac265-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="ac265-229">In PowerShell is het verschil tussen beleidsregels voor veilige bijlagen en regels voor veilige bijlagen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="ac265-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="ac265-230">U beheert beleidsregels voor veilige bijlagen met behulp van **\* de cmdlets -SafeAttachmentPolicy** en u beheert regels voor veilige bijlagen met de **\* cmdlets -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="ac265-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="ac265-231">In PowerShell maakt u eerst het beleid voor veilige bijlagen en vervolgens maakt u de veilige bijlageregel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ac265-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ac265-232">In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="ac265-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="ac265-233">Wanneer u een veilig bijlagebeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige bijlagen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="ac265-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="ac265-234">PowerShell gebruiken om beleid voor veilige bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="ac265-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="ac265-235">Het maken van een beleid voor veilige bijlagen in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="ac265-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ac265-236">Maak het beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ac265-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="ac265-237">Maak de veilige bijlageregel die het beleid voor veilige bijlagen aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ac265-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="ac265-238">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ac265-238">**Notes**:</span></span>

- <span data-ttu-id="ac265-239">U kunt een nieuwe veilige bijlageregel maken en er een bestaand, niet-verbonden beleid voor veilige bijlagen aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="ac265-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="ac265-240">Een veilige bijlageregel kan niet worden gekoppeld aan meer dan één beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ac265-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="ac265-241">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige bijlagen in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="ac265-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="ac265-242">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="ac265-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="ac265-243">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="ac265-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="ac265-244">Een nieuw beleid voor veilige bijlagen dat u in PowerShell maakt, is pas zichtbaar in het Beveiligings- & Compliancecentrum als u het beleid aan een veilige bijlageregel toewijst.</span><span class="sxs-lookup"><span data-stu-id="ac265-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="ac265-245">Stap 1: PowerShell gebruiken om een veilig bijlagebeleid te maken</span><span class="sxs-lookup"><span data-stu-id="ac265-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="ac265-246">Als u een beleid voor veilige bijlagen wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="ac265-247">In dit voorbeeld wordt een beleid voor veilige bijlagen met de naam Contoso All gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="ac265-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="ac265-248">Blokkeer berichten die malware bevatten door het scannen van veilige documenten (we gebruiken de _parameter_ Actie niet en de standaardwaarde is `Block` ).</span><span class="sxs-lookup"><span data-stu-id="ac265-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="ac265-249">Omleiding is ingeschakeld en berichten die malware bevatten, worden naar sec-ops@contoso.com verzonden voor analyse en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="ac265-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="ac265-250">Als het scannen van veilige bijlagen niet beschikbaar is of als er fouten optreden, kunt u het bericht niet verzenden (we gebruiken de parameter _ActionOnError_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="ac265-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="ac265-251">Zie [New-SafeAttachmentPolicy (Nieuw-SafeAttachmentPolicy)](/powershell/module/exchange/new-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="ac265-252">Stap 2: PowerShell gebruiken om een veilige bijlageregel te maken</span><span class="sxs-lookup"><span data-stu-id="ac265-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="ac265-253">Als u een veilige bijlageregel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="ac265-254">In dit voorbeeld wordt een veilige bijlageregel met de naam Contoso All gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="ac265-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="ac265-255">De regel is gekoppeld aan het beleid voor veilige bijlagen met de naam Contoso All.</span><span class="sxs-lookup"><span data-stu-id="ac265-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="ac265-256">De regel is van toepassing op alle geadresseerden in het contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="ac265-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="ac265-257">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ac265-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="ac265-258">De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="ac265-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="ac265-259">Zie [New-SafeAttachmentRule voor](/powershell/module/exchange/new-safeattachmentrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="ac265-260">PowerShell gebruiken om beleidsregels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="ac265-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="ac265-261">Gebruik de volgende syntaxis als u bestaande beleidsregels voor veilige bijlagen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="ac265-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ac265-262">In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige bijlagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ac265-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="ac265-263">Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige bijlagen met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="ac265-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ac265-264">Zie [Get-SafeAttachmentPolicy (Get-SafeAttachmentPolicy)](/powershell/module/exchange/get-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="ac265-265">PowerShell gebruiken om regels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="ac265-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="ac265-266">Als u bestaande regels voor veilige bijlagen wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ac265-267">In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige bijlagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ac265-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="ac265-268">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="ac265-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="ac265-269">Dit voorbeeld retourneert gedetailleerde informatie voor de veilige bijlageregel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="ac265-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ac265-270">Zie [Get-SafeAttachmentRule (Get-SafeAttachmentRule)](/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="ac265-271">PowerShell gebruiken om beleidsregels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ac265-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="ac265-272">U kunt de naam van een beleid voor veilige bijlagen niet wijzigen in PowerShell (de cmdlet **Set-SafeAttachmentPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="ac265-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ac265-273">Wanneer u de naam van een beleid voor veilige bijlagen wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _bijlagen._</span><span class="sxs-lookup"><span data-stu-id="ac265-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="ac265-274">Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige bijlagen maakt, zoals wordt beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) gebruiken om eerder in dit artikel een sectie voor het beleid voor veilige bijlagen te maken.</span><span class="sxs-lookup"><span data-stu-id="ac265-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="ac265-275">Als u een beleid voor veilige bijlagen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ac265-276">Zie [Set-SafeAttachmentPolicy (Set-SafeAttachmentPolicy)](/powershell/module/exchange/set-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="ac265-277">PowerShell gebruiken om regels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ac265-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="ac265-278">De enige instelling die niet beschikbaar is wanneer u een veilige bijlageregel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="ac265-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ac265-279">Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ac265-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="ac265-280">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: Gebruik PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) om eerder in dit artikel een sectie met veilige bijlageregel te maken.</span><span class="sxs-lookup"><span data-stu-id="ac265-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="ac265-281">Als u een veilige bijlageregel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ac265-282">Zie [Set-SafeAttachmentRule (Set-SafeAttachmentRule)](/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="ac265-283">PowerShell gebruiken om regels voor veilige bijlagen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="ac265-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="ac265-284">Als u een veilige bijlageregel in PowerShell in- of uitschakelen, wordt het hele beleid voor veilige bijlagen (de veilige bijlageregel en het toegewezen beleid voor veilige bijlagen) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac265-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="ac265-285">Als u een veilige bijlageregel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="ac265-286">In dit voorbeeld wordt de veilige bijlageregel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac265-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ac265-287">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ac265-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ac265-288">Zie [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule (Enable-SafeAttachmentRule en Disable-SafeAttachmentRule)](/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="ac265-289">PowerShell gebruiken om de prioriteit van regels voor veilige bijlagen in te stellen</span><span class="sxs-lookup"><span data-stu-id="ac265-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="ac265-290">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="ac265-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ac265-291">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="ac265-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ac265-292">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ac265-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ac265-293">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="ac265-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ac265-294">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="ac265-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ac265-295">Als u de prioriteit van een veilige bijlageregel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ac265-296">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="ac265-296">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ac265-297">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="ac265-297">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ac265-298">**Opmerking:** Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="ac265-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="ac265-299">Zie [Set-SafeAttachmentRule (Set-SafeAttachmentRule)](/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="ac265-300">PowerShell gebruiken om beleid voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ac265-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="ac265-301">Wanneer u PowerShell gebruikt om een beleid voor veilige bijlagen te verwijderen, wordt de bijbehorende regel voor veilige bijlagen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ac265-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="ac265-302">Als u een beleid voor veilige bijlagen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ac265-303">In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ac265-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ac265-304">Zie [Remove-SafeAttachmentPolicy (Remove-SafeAttachmentPolicy)](/powershell/module/exchange/remove-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="ac265-305">PowerShell gebruiken om regels voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ac265-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="ac265-306">Wanneer u PowerShell gebruikt om een veilige bijlageregel te verwijderen, wordt het bijbehorende beleid voor veilige bijlagen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ac265-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="ac265-307">Als u een veilige bijlageregel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ac265-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="ac265-308">In dit voorbeeld wordt de veilige bijlageregel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ac265-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ac265-309">Zie [Remove-SafeAttachmentRule (Remove-SafeAttachmentRule)](/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="ac265-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ac265-310">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="ac265-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="ac265-311">Ga als volgt te werk om te controleren of u beleidsregels voor veilige bijlagen hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="ac265-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="ac265-312">Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="ac265-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="ac265-313">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="ac265-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ac265-314">Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.</span><span class="sxs-lookup"><span data-stu-id="ac265-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="ac265-315">Vervang in Exchange Online PowerShell of Exchange Online Protection PowerShell de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:</span><span class="sxs-lookup"><span data-stu-id="ac265-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="ac265-316">Als u wilt controleren of veilige bijlagen berichten scannen, controleert u de beschikbare Defender voor Office 365-rapporten.</span><span class="sxs-lookup"><span data-stu-id="ac265-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="ac265-317">Zie Rapporten voor Defender voor [Office 365](view-reports-for-atp.md) en Verkenner gebruiken in het beveiligings- [& compliancecentrum voor meer informatie.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="ac265-317">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>