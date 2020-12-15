---
title: Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Meer informatie over het definiëren van beleidsregels voor veilige bijlagen om uw organisatie tegen kwaadwillende bestanden in een e-mail te beschermen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9105e7ed9e9bc376b3d86cd846d8c1d6eae8deea
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682902"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2b007-103">Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2b007-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="2b007-104">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="2b007-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="2b007-105">Als u een thuisgebruiker bent die op zoek bent naar informatie over het scannen van bijlagen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="2b007-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2b007-106">Veilige bijlagen is een functie in [Microsoft Defender voor Office 365](office-365-atp.md) waarbij een virtuele omgeving wordt gebruikt voor het controleren van bijlagen in inkomende e-mailberichten nadat ze zijn gescand door [beveiliging tegen malware in Exchange Online Protection (EOP)](anti-malware-protection.md), maar voordat ze worden bezorgd voor geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2b007-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="2b007-107">Zie voor meer informatie [veilige bijlagen in Microsoft Defender voor Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="2b007-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="2b007-108">Er is geen ingebouwd of standaardbeleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="2b007-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="2b007-109">Als u veilig bijlagen wilt scannen van bijlagen bij e-mailberichten, moet u een of meer beleidsregels voor veilige bijlagen maken, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2b007-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="2b007-110">U kunt beleidsregels voor veilige bijlagen in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell) configureren voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met invoegtoepassingen voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b007-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="2b007-111">De basiselementen van een veilig bijlage beleid zijn:</span><span class="sxs-lookup"><span data-stu-id="2b007-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="2b007-112">Met **het beleid voor veilige bijlagen**: Hiermee geeft u de acties voor onbekende detectie van malware op, of u berichten met schadelijke software wilt verzenden naar een opgegeven e-mailadres en of u berichten wilt bezorgen als het scannen van veilige bijlagen niet mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="2b007-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="2b007-113">Met **de veilige bijlage regel**: Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (waarvoor het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="2b007-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="2b007-114">Het verschil tussen deze twee elementen is niet duidelijk wanneer u beveiligingsmaatregelen voor veilige bijlagen beheert in de beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="2b007-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2b007-115">Wanneer u een beleid voor veilige bijlagen maakt, maakt u eigenlijk een veilige bijlage regel en het bijbehorende veilige bijlage beleid tegelijk met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="2b007-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="2b007-116">Wanneer u een veilig bijlage beleid wijzigt, worden de instellingen voor de naam, de prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden gewijzigd in de veilige bijlage regel.</span><span class="sxs-lookup"><span data-stu-id="2b007-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="2b007-117">Alle andere instellingen wijzigen het bijbehorende veilige bijlage beleid.</span><span class="sxs-lookup"><span data-stu-id="2b007-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="2b007-118">Wanneer u een beleid voor veilige bijlagen verwijdert, worden de veilige bijlage regel en het bijbehorende veilige bijlage beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b007-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="2b007-119">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="2b007-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="2b007-120">Zie voor meer informatie de sectie [Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken voor het configureren](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) van de sectie voor het opstellen van veilige bijlagen verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2b007-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="2b007-121">In het gebied algemene instellingen van instellingen voor veilige bijlagen configureert u functies die niet afhankelijk zijn van beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="2b007-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="2b007-122">Zie [ATP voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) en [veilige documenten in Microsoft 365 E5](safe-docs.md)inschakelen voor instructies.</span><span class="sxs-lookup"><span data-stu-id="2b007-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2b007-123">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2b007-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2b007-124">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2b007-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2b007-125">Als u rechtstreeks naar de pagina met **veilige bijlagen** wilt gaan, gebruikt u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="2b007-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="2b007-126">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b007-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2b007-127">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b007-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2b007-128">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="2b007-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2b007-129">Als u beleidsregels voor veilige bijlagen wilt maken, wijzigen en verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="2b007-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2b007-130">Voor alleen-lezen toegang tot beveiligingsbeleid voor veilige bijlagen moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="2b007-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2b007-131">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="2b007-132">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="2b007-132">**Notes**:</span></span>

  - <span data-ttu-id="2b007-133">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b007-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2b007-134">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="2b007-135">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="2b007-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="2b007-136">Zie [instellingen voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)voor de aanbevolen instellingen voor beleidsregels voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="2b007-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="2b007-137">Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="2b007-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="2b007-138">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor het maken van veilige bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="2b007-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="2b007-139">Als u een aangepast veilig bijlagebeleid maakt in de beveiligings & nalevings centrum, wordt de veilige bijlage regel en het bijbehorende veilige bijlage beleid tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="2b007-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="2b007-140">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2b007-141">Klik op de pagina met **veilige bijlagen** op **maken**.</span><span class="sxs-lookup"><span data-stu-id="2b007-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="2b007-142">De wizard **nieuwe beleidsregels voor veilige bijlagen** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="2b007-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="2b007-143">Configureer de volgende instellingen op de pagina **naam van uw beleid** :</span><span class="sxs-lookup"><span data-stu-id="2b007-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="2b007-144">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="2b007-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="2b007-145">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="2b007-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="2b007-146">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2b007-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2b007-147">Configureer de volgende instellingen op de pagina **instellingen** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2b007-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2b007-148">**Veilige bijlagen onbekende schadelijk malware-antwoord**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2b007-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="2b007-149">**Uit**: meestal wordt deze waarde niet aangeraden.</span><span class="sxs-lookup"><span data-stu-id="2b007-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="2b007-150">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="2b007-150">**Monitor**</span></span>
     - <span data-ttu-id="2b007-151">**Blok**: dit is de standaardwaarde en de aanbevolen waarde in de standaard en strikte [vooraf ingestelde beveiligingsbeleidsregels](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2b007-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="2b007-152">**Vervangen**</span><span class="sxs-lookup"><span data-stu-id="2b007-152">**Replace**</span></span>
     - <span data-ttu-id="2b007-153">**Dynamische bezorging (preview-functie)**</span><span class="sxs-lookup"><span data-stu-id="2b007-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="2b007-154">Deze waarden worden uitgelegd in de [beleidsinstellingen voor veilige bijlagen](atp-safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="2b007-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="2b007-155">**Verzend de bijlage naar het volgende e-mailadres**: voor de actiewaarden **blokkeren**, **volgen** of **vervangen**, kunt u **omleiden inschakelen** selecteren voor het verzenden van berichten met bijlagen met schadelijke software naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="2b007-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="2b007-156">De aanbeveling voor standaard-en strikte beleidsinstellingen is om omleiding in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="2b007-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="2b007-157">Zie [instellingen voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="2b007-158">**De bovenstaande selectie toepassen als u wilt dat malware wordt gescand op bijlagen wanneer een fout optreedt of als de fout zich voordoet**, wordt de actie die is opgegeven door veilige bijlagen, ook wel als gevolg van **schadelijke malware** op berichten.</span><span class="sxs-lookup"><span data-stu-id="2b007-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="2b007-159">Altijd deze optie selecteren als u **ingeschakelde omleiding** selecteert.</span><span class="sxs-lookup"><span data-stu-id="2b007-159">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="2b007-160">Anders zijn er mogelijk berichten verloren.</span><span class="sxs-lookup"><span data-stu-id="2b007-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="2b007-161">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2b007-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2b007-162">Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="2b007-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="2b007-163">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="2b007-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="2b007-164">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="2b007-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="2b007-165">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="2b007-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="2b007-166">Klik op **een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2b007-166">Click **Add a condition**.</span></span> <span data-ttu-id="2b007-167">Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als**:</span><span class="sxs-lookup"><span data-stu-id="2b007-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="2b007-168">**De ontvanger is**: geeft een of meer postvakken, e-mail gebruikers of e-mail contactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="2b007-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="2b007-169">**De ontvanger is lid van**: Hiermee geeft u een of meer groepen op in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="2b007-170">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="2b007-171">Wanneer u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzelijst weergegeven met een **van deze** vakken.</span><span class="sxs-lookup"><span data-stu-id="2b007-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="2b007-172">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="2b007-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="2b007-173">Klik in het vak en begin te typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2b007-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="2b007-174">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="2b007-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="2b007-175">Als u afzonderlijke vermeldingen wilt verwijderen **, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde.</span><span class="sxs-lookup"><span data-stu-id="2b007-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="2b007-176">Als u de hele voorwaarde wilt verwijderen **, klikt u op** ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="2b007-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="2b007-177">Als u een extra voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een resterende waarde onder **toegepast als**.</span><span class="sxs-lookup"><span data-stu-id="2b007-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="2b007-178">Als u uitzonderingen wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een uitzondering onder **behalve als**.</span><span class="sxs-lookup"><span data-stu-id="2b007-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="2b007-179">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="2b007-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="2b007-180">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2b007-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2b007-181">Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2b007-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="2b007-182">U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2b007-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="2b007-183">Wanneer u klaar bent, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="2b007-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="2b007-184">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="2b007-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="2b007-185">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2b007-186">Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="2b007-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="2b007-187">De beleidsdetails worden in een uitgelichte vlucht weergegeven</span><span class="sxs-lookup"><span data-stu-id="2b007-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="2b007-188">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="2b007-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="2b007-189">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2b007-190">Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="2b007-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="2b007-191">Klik in de beleidsdetails die worden weergegeven, op **beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="2b007-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="2b007-192">De beschikbare instellingen in de vlucht die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie [het beveiligings & gebruiken om de beleidsregels voor het maken van veilige bijlagen te maken](#use-the-security--compliance-center-to-create-safe-attachments-policies) .</span><span class="sxs-lookup"><span data-stu-id="2b007-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="2b007-193">Zie de volgende secties als u een beleid wilt in-of uitschakelen of de prioriteitsvolgorde voor beleidsregels wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="2b007-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="2b007-194">Beleidsregels voor veilige bijlagen in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="2b007-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="2b007-195">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2b007-196">Let op de waarde in de kolom **status** :</span><span class="sxs-lookup"><span data-stu-id="2b007-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="2b007-197">Zet de wisselknop naar links</span><span class="sxs-lookup"><span data-stu-id="2b007-197">Move the toggle to the left</span></span> ![Beleid uitschakelen](../../media/scc-toggle-off.png) <span data-ttu-id="2b007-199">om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="2b007-199">to disable the policy.</span></span>

   - <span data-ttu-id="2b007-200">De wisselknop naar rechts verplaatsen</span><span class="sxs-lookup"><span data-stu-id="2b007-200">Move the toggle to the right</span></span> ![Beleid inschakelen](../../media/scc-toggle-on.png) <span data-ttu-id="2b007-202">het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="2b007-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="2b007-203">De prioriteit voor beleidsregels voor veilige bijlagen instellen</span><span class="sxs-lookup"><span data-stu-id="2b007-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="2b007-204">Beleidsregels voor veilige bijlagen krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwe policies zijn een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="2b007-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="2b007-205">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="2b007-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="2b007-206">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="2b007-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="2b007-207">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="2b007-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="2b007-208">Beleidsregels voor veilige bijlagen worden weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0).</span><span class="sxs-lookup"><span data-stu-id="2b007-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="2b007-209">**Opmerking**: in het beveiligings & nalevings centrum kunt u de prioriteit van het beleid voor veilige bijlagen alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2b007-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="2b007-210">In PowerShell kunt u de standaardprioriteit negeren wanneer u de veilige bijlage regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="2b007-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="2b007-211">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="2b007-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="2b007-212">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2b007-213">Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="2b007-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="2b007-214">Voor de details van het beleid dat wordt weergegeven, klikt u op de knop beschikbare prioriteit.</span><span class="sxs-lookup"><span data-stu-id="2b007-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="2b007-215">Voor het beleid voor veilige bijlagen met de **prioriteits** waarde **0** is slechts de knop **prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2b007-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="2b007-216">Het beleid voor veilige bijlagen met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is alleen beschikbaar voor de knop **prioriteit verhogen** .</span><span class="sxs-lookup"><span data-stu-id="2b007-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="2b007-217">Als u beschikt over drie of meer regels voor het veilig maken van bijlagen, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="2b007-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="2b007-218">Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2b007-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="2b007-219">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="2b007-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="2b007-220">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="2b007-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="2b007-221">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2b007-222">Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="2b007-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="2b007-223">Ga naar de details van het beleid dat wordt weergegeven, klik op **beleid verwijderen** en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2b007-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="2b007-224">PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken voor het configureren van de beleidsregels voor veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="2b007-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="2b007-225">Zoals hierboven beschreven, bestaat een beleid voor veilige bijlagen van een veilig bijlage beleid en een veilige bijlage regel.</span><span class="sxs-lookup"><span data-stu-id="2b007-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="2b007-226">In PowerShell is het verschil tussen veilig bijlage beleid en veilige bijlage regels zichtbaar.</span><span class="sxs-lookup"><span data-stu-id="2b007-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="2b007-227">U beheert de beleidsregels voor veilige bijlagen met behulp van de **\* SafeAttachmentPolicy-** cmdlets en u beheert veilige bijlage regels met behulp van de cmdlets voor **\* SafeAttachmentRule** .</span><span class="sxs-lookup"><span data-stu-id="2b007-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="2b007-228">In PowerShell maakt u eerst een veilig bijlagebeleid en vervolgens maakt u de veilige bijlage regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="2b007-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="2b007-229">In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="2b007-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="2b007-230">Wanneer u een veilig bijlage beleid verwijdert uit PowerShell, wordt de bijbehorende veilige bijlage regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="2b007-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="2b007-231">PowerShell gebruiken om beleid voor veilige bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="2b007-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="2b007-232">Het maken van een beleid voor veilige bijlagen in PowerShell is een procedure die bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="2b007-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="2b007-233">Maak een veilig bijlage beleid.</span><span class="sxs-lookup"><span data-stu-id="2b007-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="2b007-234">Maak de veilige bijlage regel waarmee het veilige bijlage beleid wordt opgegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="2b007-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="2b007-235">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="2b007-235">**Notes**:</span></span>

- <span data-ttu-id="2b007-236">U kunt een nieuwe veilige bijlage regel maken en een bestaand, niet-gekoppeld veilig bijlage beleid toewijzen.</span><span class="sxs-lookup"><span data-stu-id="2b007-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="2b007-237">Een veilige bijlage regel kan niet worden gekoppeld aan meer dan één veilig bijlage beleid.</span><span class="sxs-lookup"><span data-stu-id="2b007-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="2b007-238">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige bijlagen in PowerShell die niet beschikbaar zijn in het beveiligings & nalevings centrum voordat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="2b007-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="2b007-239">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe SafeAttachmentRule-** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="2b007-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="2b007-240">De prioriteit van het beleid instellen voor het maken van de _\<Number\>_ **nieuwe SafeAttachmentRule-** cmdlet (prioriteit).</span><span class="sxs-lookup"><span data-stu-id="2b007-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="2b007-241">Een nieuw beleid voor veilige bijlagen dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een veilige regel regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="2b007-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="2b007-242">Stap 1: PowerShell gebruiken om een veilig bijlage beleid te maken</span><span class="sxs-lookup"><span data-stu-id="2b007-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="2b007-243">U maakt een veilig bijlage beleid met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="2b007-244">In dit voorbeeld wordt een veilig bijlage beleid met de naam contoso gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2b007-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="2b007-245">Het blokkeren van berichten die malware bevatten door veilige documenten te scannen (we gebruiken de _actie_ parameter niet en de standaardwaarde is `Block` ).</span><span class="sxs-lookup"><span data-stu-id="2b007-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="2b007-246">Omleiding is ingeschakeld, en berichten die schadelijke software bevatten, worden verzonden naar sec-ops@contoso.com voor analyse en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="2b007-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="2b007-247">Als het scannen van veilige bijlagen niet beschikbaar is of fouten ondervindt, moet u het bericht niet bezorgen (de parameter _ActionOnError_ wordt niet gebruikt en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="2b007-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="2b007-248">Zie [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="2b007-249">Stap 2: PowerShell gebruiken om een veilige bijlage regel te maken</span><span class="sxs-lookup"><span data-stu-id="2b007-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="2b007-250">Als u een veilige bijlage regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="2b007-251">In dit voorbeeld wordt een veilige bijlage regel gemaakt met de naam contoso all met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="2b007-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="2b007-252">De regel is gekoppeld aan het veilige bijlage beleid, genaamd contoso all.</span><span class="sxs-lookup"><span data-stu-id="2b007-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="2b007-253">De regel geldt voor alle geadresseerden in het contoso.com-domein.</span><span class="sxs-lookup"><span data-stu-id="2b007-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="2b007-254">Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2b007-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="2b007-255">De regel is ingeschakeld (de _ingeschakelde_ parameter wordt niet gebruikt en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="2b007-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="2b007-256">Zie [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="2b007-257">PowerShell gebruiken om veilige bijlage beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="2b007-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="2b007-258">Gebruik de volgende syntaxis om de bestaande beleidsregels voor veilige bijlagen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="2b007-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2b007-259">In dit voorbeeld wordt een overzichtslijst weergegeven met alle beleidsregels voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="2b007-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="2b007-260">In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor het beleid voor veilige bijlagen met de naam contoso-leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="2b007-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="2b007-261">Zie [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="2b007-262">PowerShell gebruiken om veilige bijlage regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="2b007-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="2b007-263">Als u bestaande regels voor veilige bijlagen wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2b007-264">In dit voorbeeld wordt een overzichtslijst met alle veilige bijlage regels geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="2b007-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="2b007-265">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="2b007-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="2b007-266">In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de veilige bijlage regel genaamd contoso-leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="2b007-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="2b007-267">Zie [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="2b007-268">PowerShell gebruiken om een veilig bijlage beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="2b007-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="2b007-269">U kunt de naam van een veilig bijlage beleid in PowerShell niet wijzigen (de cmdlet **set-SafeAttachmentPolicy** heeft geen _naam_ parameter).</span><span class="sxs-lookup"><span data-stu-id="2b007-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="2b007-270">Wanneer u de naam van een beleid voor veilige bijlagen in het beveiligings & nalevings centrum wijzigt, kunt u alleen de naam van de veilige bijlage _regel_ wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2b007-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="2b007-271">U kunt ook dezelfde instellingen gebruiken als u een veilig bijlage beleid maakt zoals wordt beschreven in de sectie [stap 1: PowerShell gebruiken voor het maken van een veilig bijlage](#step-1-use-powershell-to-create-a-safe-attachment-policy) gedeelte eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2b007-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="2b007-272">Als u een veilig bijlage beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="2b007-273">Zie [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="2b007-274">PowerShell gebruiken om veilige bijlage regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="2b007-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="2b007-275">De enige instelling die niet beschikbaar is wanneer u een veilige bijlage regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="2b007-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="2b007-276">Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="2b007-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="2b007-277">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals wordt beschreven in de sectie [stap 2: PowerShell gebruiken om een veilige bijlage regel te maken](#step-2-use-powershell-to-create-a-safe-attachment-rule) eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="2b007-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="2b007-278">Als u een veilige bijlage regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="2b007-279">Zie [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="2b007-280">PowerShell gebruiken om veilige bijlage regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="2b007-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="2b007-281">Als u een veilige bijlage regel in-of uitschakelt in PowerShell, wordt het hele beleid voor veilige bijlagen (de veilige bijlage regel en het toegewezen beleid) uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2b007-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="2b007-282">Als u een veilige bijlage regel wilt in-of uitschakelen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="2b007-283">In dit voorbeeld wordt de veilige bijlage regel genaamd marketing afdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2b007-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="2b007-284">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2b007-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="2b007-285">Zie [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) en [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="2b007-286">PowerShell gebruiken om de prioriteit van veilige bijlage regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="2b007-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="2b007-287">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="2b007-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="2b007-288">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="2b007-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="2b007-289">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2b007-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="2b007-290">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="2b007-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="2b007-291">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="2b007-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="2b007-292">Als u de prioriteit wilt instellen voor een veilige bijlage regel in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="2b007-293">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="2b007-293">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="2b007-294">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="2b007-294">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="2b007-295">**Opmerking**: als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-SafeAttachmentRule** .</span><span class="sxs-lookup"><span data-stu-id="2b007-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="2b007-296">Zie [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="2b007-297">PowerShell gebruiken om een veilig bijlage beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="2b007-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="2b007-298">Wanneer u PowerShell gebruikt om een veilig bijlage beleid te verwijderen, wordt de bijbehorende veilige bijlage regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b007-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="2b007-299">Als u een veilig bijlage beleid wilt verwijderen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="2b007-300">In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b007-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="2b007-301">Zie [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="2b007-302">PowerShell gebruiken om veilige bijlage regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="2b007-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="2b007-303">Wanneer u PowerShell gebruikt om een veilige bijlage regel te verwijderen, wordt het bijbehorende veilige bijlage beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b007-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="2b007-304">Als u een veilige bijlage regel wilt verwijderen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b007-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="2b007-305">In dit voorbeeld wordt de veilige bijlage regel genaamd marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b007-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="2b007-306">Zie [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2b007-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2b007-307">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="2b007-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="2b007-308">Voer een van de volgende stappen uit om te controleren of u het beleid voor veilige bijlagen hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="2b007-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="2b007-309">Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.</span><span class="sxs-lookup"><span data-stu-id="2b007-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="2b007-310">Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** .</span><span class="sxs-lookup"><span data-stu-id="2b007-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="2b007-311">Als u meer informatie wilt bekijken, selecteert u het beleid in de lijst en bekijkt u de details in de vlucht.</span><span class="sxs-lookup"><span data-stu-id="2b007-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="2b007-312">In Exchange Online PowerShell of Exchange Online Protection PowerShell vervangt u \<Name\> de naam van het beleid of de regel door de volgende opdracht uit te voeren en de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="2b007-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="2b007-313">Controleer de rapporten over de beschikbare Defender voor Office 365 om te controleren of veilige bijlagen berichten controleren.</span><span class="sxs-lookup"><span data-stu-id="2b007-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="2b007-314">Voor meer informatie raadpleegt u [rapporten weergeven voor Defender voor Office 365](view-reports-for-atp.md) en [gebruikt u de Verkenner in het beveiligings & nalevings centrum](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="2b007-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
