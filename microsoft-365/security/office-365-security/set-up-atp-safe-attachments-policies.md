---
title: Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365
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
ms.openlocfilehash: 9343ce222f1deb84e900f0d6f18e7d55daa73372
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084611"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e1644-103">Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e1644-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="e1644-104">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="e1644-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="e1644-105">Als u een thuisgebruiker bent en op zoek bent naar informatie over het scannen van bijlagen in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="e1644-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e1644-106">Veilige bijlagen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) die een virtuele omgeving gebruikt om bijlagen in binnenkomende e-mailberichten te controleren nadat ze zijn gescand met beveiliging tegen [malware in Exchange Online Protection (EOP),](anti-malware-protection.md)maar voordat deze worden bezorgd bij geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="e1644-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="e1644-107">Zie Veilige bijlagen in Microsoft Defender voor [Office 365](atp-safe-attachments.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="e1644-108">Er is geen ingebouwd of standaardbeleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e1644-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="e1644-109">Als u wilt dat bijlagen met veilige bijlagen worden gescand in e-mailberichten, moet u een of meer beleidsregels voor veilige bijlagen maken, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e1644-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="e1644-110">U kunt het beleid voor veilige bijlagen configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="e1644-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="e1644-111">De basiselementen van een beleid met veilige bijlagen zijn:</span><span class="sxs-lookup"><span data-stu-id="e1644-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="e1644-112">Het beleid voor veilige **bijlagen:** hiermee geeft u de acties op voor onbekende malwaredetecties, of berichten met malware-bijlagen moeten worden verzonden naar een opgegeven e-mailadres en of berichten moeten worden verzonden als veilige bijlagen niet kunnen worden gescand.</span><span class="sxs-lookup"><span data-stu-id="e1644-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="e1644-113">**De regel voor veilige bijlagen:** hiermee geeft u de prioriteit- en geadresseerdefilters op (op wie het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="e1644-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="e1644-114">Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid Veilige bijlagen beheert in het & Compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="e1644-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e1644-115">Wanneer u een beleid voor veilige bijlagen maakt, maakt u tegelijkertijd een veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="e1644-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e1644-116">Wanneer u een beleid voor veilige bijlagen wijzigt, worden instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en geadresseerdenfilters de regel voor veilige bijlagen gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e1644-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="e1644-117">Met alle andere instellingen wordt het bijbehorende beleid voor veilige bijlagen gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e1644-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="e1644-118">Wanneer u een beleid voor veilige bijlagen verwijdert, worden de regels voor veilige bijlagen en het bijbehorende beleid voor veilige bijlagen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e1644-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="e1644-119">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="e1644-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e1644-120">Zie de sectie Exchange Online PowerShell of de zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) gebruiken om beleidsregels voor veilige bijlagen verderop in dit artikel te configureren.</span><span class="sxs-lookup"><span data-stu-id="e1644-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="e1644-121">In het gebied met globale instellingen van de instellingen voor veilige bijlagen configureert u functies die niet afhankelijk zijn van het beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e1644-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="e1644-122">Zie Veilige bijlagen [in microsoft](turn-on-atp-for-spo-odb-and-teams.md) 365 E5 in microsoft [365 E5](safe-docs.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e1644-122">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e1644-123">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e1644-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e1644-124">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e1644-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e1644-125">Als u rechtstreeks naar de **pagina Veilige bijlagen wilt** gaan, gebruikt u <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="e1644-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="e1644-126">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1644-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e1644-127">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1644-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e1644-128">U moet machtigingen toegewezen krijgen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e1644-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e1644-129">Als u een beleid voor veilige bijlagen wilt maken, wijzigen en  verwijderen, moet u lid zijn van  de rollengroepen  Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- &-compliancecentrum en lid zijn van de rollengroep Organisatiebeheer in Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="e1644-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="e1644-130">Voor alleen-lezen toegang tot beleidsregels voor veilige bijlagen  moet u  lid zijn van de rollengroepen Globale lezer of Beveiligingslezer in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="e1644-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="e1644-131">Zie Machtigingen in [het beveiligings-](permissions-in-the-security-and-compliance-center.md) en & en [machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e1644-132">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="e1644-132">**Notes**:</span></span>

  - <span data-ttu-id="e1644-133">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1644-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e1644-134">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e1644-135">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="e1644-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e1644-136">Zie Instellingen voor veilige bijlagen voor de aanbevolen instellingen voor het beleid [voor veilige bijlagen.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="e1644-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="e1644-137">Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="e1644-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="e1644-138">Het beveiligings- & gebruiken om beleid voor veilige bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="e1644-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="e1644-139">Als u een aangepast beleid voor veilige bijlagen maakt in het beveiligings- & Compliancecentrum, worden de regels voor veilige bijlagen en het bijbehorende beleid voor veilige bijlagen op hetzelfde moment met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e1644-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="e1644-140">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="e1644-141">Klik op **de pagina Veilige bijlagen** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="e1644-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="e1644-142">De **wizard Nieuwe veilige bijlagen wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="e1644-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="e1644-143">Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:</span><span class="sxs-lookup"><span data-stu-id="e1644-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e1644-144">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="e1644-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="e1644-145">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="e1644-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e1644-146">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="e1644-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e1644-147">Configureer **de volgende** instellingen op de pagina Instellingen die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e1644-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e1644-148">**Safe Attachments unknown malware response**: Select one of the following values:</span><span class="sxs-lookup"><span data-stu-id="e1644-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="e1644-149">**Uit:** deze waarde wordt meestal niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="e1644-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="e1644-150">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="e1644-150">**Monitor**</span></span>
     - <span data-ttu-id="e1644-151">**Blokkeren:** dit is de standaardwaarde en de aanbevolen waarde in standaard- en [strikt vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e1644-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="e1644-152">**Vervangen**</span><span class="sxs-lookup"><span data-stu-id="e1644-152">**Replace**</span></span>
     - <span data-ttu-id="e1644-153">**Dynamische bezorging (preview-functie)**</span><span class="sxs-lookup"><span data-stu-id="e1644-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="e1644-154">Deze waarden worden uitgelegd in [de beleidsinstellingen voor veilige bijlagen.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="e1644-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="e1644-155">Verstuur de bijlage naar het volgende e-mailadres: voor de actiewaarden  **Blokkeren,** Controleren of **Vervangen,** kunt u Omleiden inschakelen selecteren om berichten met malwarebijlagen te verzenden naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.  </span><span class="sxs-lookup"><span data-stu-id="e1644-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="e1644-156">De aanbeveling voor standaard- en strikte beleidsinstellingen is om omleiding in teschakelen.</span><span class="sxs-lookup"><span data-stu-id="e1644-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="e1644-157">Zie instellingen voor [veilige bijlagen voor meer informatie.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="e1644-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="e1644-158">**Pas de bovenstaande** selectie toe als malware wordt gescand op bijlagen in de tijd of als er een fout optreedt: De actie die wordt opgegeven door Safe **Attachments unknown malware response** wordt uitgevoerd op berichten, zelfs als safe attachments scannen niet kan worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="e1644-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="e1644-159">Als u deze optie hebt geselecteerd, selecteert u altijd **Enabled redirect.**</span><span class="sxs-lookup"><span data-stu-id="e1644-159">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="e1644-160">Anders kunnen berichten verloren gaan.</span><span class="sxs-lookup"><span data-stu-id="e1644-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="e1644-161">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="e1644-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e1644-162">Zoek op **de** pagina Toegepast op die wordt weergegeven naar de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e1644-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="e1644-163">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="e1644-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e1644-164">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e1644-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e1644-165">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e1644-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="e1644-166">Klik **op Voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e1644-166">Click **Add a condition**.</span></span> <span data-ttu-id="e1644-167">Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="e1644-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="e1644-168">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="e1644-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e1644-169">**De geadresseerde is lid van:** Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="e1644-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="e1644-170">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="e1644-171">Nadat u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzekeuze verschijnen met een **Van deze** vakjes.</span><span class="sxs-lookup"><span data-stu-id="e1644-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="e1644-172">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="e1644-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="e1644-173">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="e1644-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="e1644-174">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="e1644-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="e1644-175">Als u afzonderlijke items wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="e1644-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="e1644-176">Als u de hele voorwaarde wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="e1644-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="e1644-177">Als u een extra voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als.**</span><span class="sxs-lookup"><span data-stu-id="e1644-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="e1644-178">Als u uitzonderingen wilt toevoegen, klikt u **op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.**</span><span class="sxs-lookup"><span data-stu-id="e1644-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="e1644-179">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="e1644-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e1644-180">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="e1644-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e1644-181">Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e1644-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="e1644-182">U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e1644-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e1644-183">Klik op Voltooien wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="e1644-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="e1644-184">Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e1644-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="e1644-185">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="e1644-186">Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e1644-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="e1644-187">De beleidsdetails worden in een fly-out weergegeven</span><span class="sxs-lookup"><span data-stu-id="e1644-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="e1644-188">Het beveiligings- & compliancecentrum gebruiken om het beleid voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e1644-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="e1644-189">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="e1644-190">Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e1644-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e1644-191">Klik in het fly-out met beleidsdetails op **Beleid bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e1644-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="e1644-192">De beschikbare instellingen in de fly out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in het [beveiligings- & Compliancecentrum](#use-the-security--compliance-center-to-create-safe-attachments-policies) gebruiken om beleidsregels voor veilige bijlagen te maken.</span><span class="sxs-lookup"><span data-stu-id="e1644-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="e1644-193">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteit wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="e1644-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="e1644-194">Beleid voor veilige bijlagen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="e1644-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="e1644-195">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="e1644-196">U ziet de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="e1644-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="e1644-197">De schakelaar naar links verplaatsen</span><span class="sxs-lookup"><span data-stu-id="e1644-197">Move the toggle to the left</span></span> ![Beleid uitschakelen](../../media/scc-toggle-off.png) <span data-ttu-id="e1644-199">om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="e1644-199">to disable the policy.</span></span>

   - <span data-ttu-id="e1644-200">De schakelknop naar rechts verplaatsen</span><span class="sxs-lookup"><span data-stu-id="e1644-200">Move the toggle to the right</span></span> ![Beleid in-/uit](../../media/scc-toggle-on.png) <span data-ttu-id="e1644-202">om het beleid in teschakelen.</span><span class="sxs-lookup"><span data-stu-id="e1644-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="e1644-203">De prioriteit van beleidsregels voor veilige bijlagen instellen</span><span class="sxs-lookup"><span data-stu-id="e1644-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="e1644-204">Het beleid voor veilige bijlagen krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin het beleid is gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="e1644-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="e1644-205">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="e1644-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e1644-206">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="e1644-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e1644-207">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e1644-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="e1644-208">Beleidsregels voor veilige bijlagen worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid **heeft** de prioriteitswaarde 0).</span><span class="sxs-lookup"><span data-stu-id="e1644-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="e1644-209">**Opmerking:** in het & compliancecentrum kunt u de prioriteit van het beleid voor veilige bijlagen alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e1644-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="e1644-210">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de veilige bijlageregel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="e1644-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="e1644-211">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="e1644-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="e1644-212">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="e1644-213">Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e1644-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e1644-214">In de beleidsdetails die worden weergegeven, klikt u op de beschikbare prioriteitknop.</span><span class="sxs-lookup"><span data-stu-id="e1644-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="e1644-215">Voor het beleid veilige bijlagen **met** prioriteitwaarde **0** is alleen de knop Prioriteit **verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e1644-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="e1644-216">Voor het beleid Veilige bijlagen met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** is alleen de knop Prioriteit **verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e1644-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="e1644-217">Als u drie of meer beleidsregels voor veilige bijlagen hebt,  zijn voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Prioriteit **verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e1644-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="e1644-218">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e1644-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="e1644-219">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="e1644-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="e1644-220">Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e1644-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="e1644-221">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="e1644-222">Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e1644-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e1644-223">Wanneer de beleidsdetails worden weergegeven, klikt u op Beleid verwijderen en klikt u vervolgens op **Ja** in het dialoogvenster met de waarschuwing dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e1644-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="e1644-224">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om beleidsregels voor veilige bijlagen te configureren</span><span class="sxs-lookup"><span data-stu-id="e1644-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="e1644-225">Zoals eerder is beschreven, bestaat een beleid voor veilige bijlagen uit een beleid voor veilige bijlagen en een veilige bijlageregel.</span><span class="sxs-lookup"><span data-stu-id="e1644-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="e1644-226">In PowerShell is het verschil tussen een beleid voor veilige bijlagen en regels voor veilige bijlagen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="e1644-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="e1644-227">U beheert het beleid voor veilige bijlagen met behulp van de cmdlets **\* -SafeAttachmentPolicy** en u beheert regels voor veilige bijlagen met behulp van de cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="e1644-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="e1644-228">In PowerShell maakt u eerst het beleid voor veilige bijlagen en maakt u vervolgens de regel voor veilige bijlagen die het beleid aangeeft dat met de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e1644-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e1644-229">In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="e1644-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="e1644-230">Wanneer u een beleid voor veilige bijlagen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige bijlagen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="e1644-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="e1644-231">PowerShell gebruiken om beleidsregels voor veilige bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="e1644-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="e1644-232">Het maken van een beleid voor veilige bijlagen in PowerShell bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="e1644-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e1644-233">Maak het beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e1644-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="e1644-234">Maak de regel voor veilige bijlagen die het beleid voor veilige bijlagen aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e1644-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="e1644-235">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="e1644-235">**Notes**:</span></span>

- <span data-ttu-id="e1644-236">U kunt een nieuwe regel voor veilige bijlagen maken en er een bestaand, niet-verbonden beleid voor veilige bijlagen aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="e1644-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="e1644-237">Een veilige bijlageregel kan niet worden gekoppeld aan meer dan één beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e1644-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="e1644-238">U kunt de volgende instellingen configureren voor nieuw beleid voor veilige bijlagen in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="e1644-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="e1644-239">Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="e1644-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="e1644-240">De prioriteit van het beleid instellen tijdens het maken _(prioriteit)_ _\<Number\>_ van de cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="e1644-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="e1644-241">Een nieuw beleid voor veilige bijlagen dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum wanneer u het beleid toewijst aan een regel voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e1644-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="e1644-242">Stap 1: PowerShell gebruiken om een veilig bijlagebeleid te maken</span><span class="sxs-lookup"><span data-stu-id="e1644-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="e1644-243">Gebruik de volgende syntaxis om een veilig bijlagebeleid te maken:</span><span class="sxs-lookup"><span data-stu-id="e1644-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="e1644-244">In dit voorbeeld wordt een beleid voor veilige bijlagen met de naam Contoso All gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="e1644-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="e1644-245">Berichten blokkeren die malware bevatten door veilige documenten te scannen (de parameter _Actie_ wordt niet gebruikt en de standaardwaarde `Block` is).</span><span class="sxs-lookup"><span data-stu-id="e1644-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="e1644-246">Omleiding is ingeschakeld en berichten die malware bevatten, worden naar het sec-ops@contoso.com voor analyse en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e1644-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="e1644-247">Als scannen van veilige bijlagen niet beschikbaar is of er fouten optreden, bezorg het bericht dan niet (de parameter _ActionOnError_ wordt niet gebruikt en de standaardwaarde `$true` is).</span><span class="sxs-lookup"><span data-stu-id="e1644-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="e1644-248">Zie [New-SafeAttachmentPolicy voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="e1644-249">Stap 2: PowerShell gebruiken om een veilige bijlageregel te maken</span><span class="sxs-lookup"><span data-stu-id="e1644-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="e1644-250">Gebruik de volgende syntaxis om een veilige bijlageregel te maken:</span><span class="sxs-lookup"><span data-stu-id="e1644-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="e1644-251">In dit voorbeeld wordt een veilige bijlageregel gemaakt met de naam Contoso Alles met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="e1644-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="e1644-252">De regel is gekoppeld aan het beleid voor veilige bijlagen met de naam Contoso All.</span><span class="sxs-lookup"><span data-stu-id="e1644-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="e1644-253">De regel is van toepassing op alle geadresseerden in contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="e1644-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="e1644-254">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e1644-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="e1644-255">De regel is ingeschakeld (de parameter _Enabled_ wordt niet gebruikt en de standaardwaarde `$true` is).</span><span class="sxs-lookup"><span data-stu-id="e1644-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="e1644-256">Zie [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="e1644-257">PowerShell gebruiken om beleidsregels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e1644-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="e1644-258">Gebruik de volgende syntaxis als u bestaand beleid voor veilige bijlagen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="e1644-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e1644-259">In dit voorbeeld wordt een overzichtslijst van alle beleidsregels voor veilige bijlagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e1644-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="e1644-260">In dit voorbeeld wordt gedetailleerde informatie gegeven over het beleid voor veilige bijlagen, genaamd Contoso-leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="e1644-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="e1644-261">Zie [Get-SafeAttachmentPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="e1644-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="e1644-262">PowerShell gebruiken om regels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e1644-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="e1644-263">Gebruik de volgende syntaxis als u bestaande regels voor veilige bijlagen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="e1644-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e1644-264">In dit voorbeeld wordt een overzichtslijst van alle regels voor veilige bijlagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e1644-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="e1644-265">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="e1644-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="e1644-266">In dit voorbeeld wordt gedetailleerde informatie gegeven over de regel voor veilige bijlagen met de naam Contoso Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="e1644-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="e1644-267">Zie [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="e1644-268">PowerShell gebruiken om beleidsregels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e1644-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="e1644-269">U kunt de naam van een beleid voor veilige bijlagen in PowerShell niet wijzigen (de cmdlet **Set-SafeAttachmentPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="e1644-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e1644-270">Wanneer u de naam van een beleid voor veilige bijlagen wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _bijlagen._</span><span class="sxs-lookup"><span data-stu-id="e1644-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="e1644-271">Anders zijn dezelfde instellingen beschikbaar wanneer u een veilig bijlagebeleid maakt, zoals wordt beschreven in stap [1: Gebruik PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) om een sectie voor het veilige bijlagebeleid te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e1644-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="e1644-272">Gebruik de volgende syntaxis om een beleid voor veilige bijlagen te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e1644-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e1644-273">Zie [Set-SafeAttachmentPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="e1644-274">PowerShell gebruiken om regels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e1644-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="e1644-275">De enige instelling die niet beschikbaar is wanneer u een regel voor veilige bijlagen wijzigt in PowerShell, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="e1644-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e1644-276">Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="e1644-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="e1644-277">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt, zoals wordt beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) gebruiken om een sectie met een veilige bijlageregel eerder in dit artikel te maken.</span><span class="sxs-lookup"><span data-stu-id="e1644-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="e1644-278">Gebruik de volgende syntaxis om een veilige bijlageregel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e1644-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e1644-279">Zie [Set-SafeAttachmentRule voor](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="e1644-280">PowerShell gebruiken om regels voor veilige bijlagen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="e1644-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="e1644-281">Als u een regel voor veilige bijlagen in PowerShell in- of uit schakelen, wordt het hele beleid voor veilige bijlagen (de regel voor veilige bijlagen en het toegewezen beleid voor veilige bijlagen) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1644-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="e1644-282">Gebruik de volgende syntaxis om een veilige bijlageregel in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="e1644-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="e1644-283">In dit voorbeeld wordt de regel voor veilige bijlagen met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1644-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="e1644-284">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1644-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="e1644-285">Zie [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) en [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="e1644-286">PowerShell gebruiken om de prioriteit van regels voor veilige bijlagen in te stellen</span><span class="sxs-lookup"><span data-stu-id="e1644-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="e1644-287">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="e1644-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e1644-288">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="e1644-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e1644-289">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e1644-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e1644-290">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="e1644-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e1644-291">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="e1644-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e1644-292">Gebruik de volgende syntaxis om de prioriteit van een regel voor veilige bijlagen in PowerShell in te stellen:</span><span class="sxs-lookup"><span data-stu-id="e1644-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e1644-293">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="e1644-293">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="e1644-294">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="e1644-294">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e1644-295">**Opmerking:** als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="e1644-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="e1644-296">Zie [Set-SafeAttachmentRule voor](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="e1644-297">PowerShell gebruiken om beleidsregels voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e1644-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="e1644-298">Wanneer u PowerShell gebruikt om een beleid voor veilige bijlagen te verwijderen, wordt de bijbehorende regel voor veilige bijlagen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e1644-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="e1644-299">Gebruik de volgende syntaxis om een beleid voor veilige bijlagen in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="e1644-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e1644-300">In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e1644-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e1644-301">Zie [Remove-SafeAttachmentPolicy voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="e1644-302">PowerShell gebruiken om regels voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e1644-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="e1644-303">Wanneer u PowerShell gebruikt om een veilige bijlageregel te verwijderen, wordt het bijbehorende beleid voor veilige bijlagen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e1644-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="e1644-304">Gebruik de volgende syntaxis om een veilige bijlageregel in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="e1644-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="e1644-305">In dit voorbeeld wordt de regel voor veilige bijlagen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e1644-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="e1644-306">Zie [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e1644-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e1644-307">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="e1644-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="e1644-308">Ga op een van de volgende stappen te werk om te controleren of u een beleid voor veilige bijlagen hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="e1644-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="e1644-309">Ga in het & compliancecentrum naar Veilige bijlagen **van** \>  \> **ATP-beleid voor bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e1644-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="e1644-310">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="e1644-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e1644-311">Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.</span><span class="sxs-lookup"><span data-stu-id="e1644-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="e1644-312">Vervang in Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="e1644-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="e1644-313">Als u wilt controleren of veilige bijlagen berichten scannen, controleert u de beschikbare Defender voor Office 365-rapporten.</span><span class="sxs-lookup"><span data-stu-id="e1644-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="e1644-314">Zie Rapporten voor Defender voor [Office 365](view-reports-for-atp.md) en Verkenner weergeven in het & compliancecentrum voor [meer informatie.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="e1644-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
