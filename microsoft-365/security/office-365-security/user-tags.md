---
title: Gebruikerslabels in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u specifieke groepen gebruikers kunt identificeren met gebruikerslabels in Microsoft Defender voor Office 365 plan 2. Tagfiltering is beschikbaar in waarschuwingen, rapporten en onderzoeken in Microsoft Defender voor Office 365 om snel de gelabelde gebruikers te identificeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44b925840700c00c6b2d28c445ac26abd6624d1c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782859"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d816b-104">Gebruikerslabels in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d816b-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="d816b-105">De functie gebruikerslabels is beschikbaar in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d816b-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="d816b-106">Voor meer informatie over de releaseplanning raadpleegt u [de Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="d816b-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="d816b-107">Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d816b-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="d816b-108">Er zijn twee typen gebruikerslabels:</span><span class="sxs-lookup"><span data-stu-id="d816b-108">There are two types of user tags:</span></span>

- <span data-ttu-id="d816b-109">**Systeemlabels:** Momenteel is [Prioriteitsaccounts](../../admin/setup/priority-accounts.md) het enige type systeemlabel.</span><span class="sxs-lookup"><span data-stu-id="d816b-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="d816b-110">**Aangepaste tags:** u maakt deze gebruikerslabels zelf.</span><span class="sxs-lookup"><span data-stu-id="d816b-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="d816b-111">Als uw organisatie Defender voor Office 365 abonnement 2 (inbegrepen in uw abonnement of als een invoegvoeggebruik) heeft, kunt u naast het gebruik van de tag prioriteitsaccounts ook aangepaste gebruikerslabels maken.</span><span class="sxs-lookup"><span data-stu-id="d816b-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="d816b-112">Momenteel kunt u alleen gebruikerslabels toepassen op postvakgebruikers.</span><span class="sxs-lookup"><span data-stu-id="d816b-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="d816b-113">Nadat u systeemlabels of aangepaste tags op gebruikers hebt toegepast, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:</span><span class="sxs-lookup"><span data-stu-id="d816b-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="d816b-114">Waarschuwingen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="d816b-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="d816b-115">Threat Explorer en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="d816b-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="d816b-116">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="d816b-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="d816b-117">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="d816b-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="d816b-118">Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) gebruiken in Exchange beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="d816b-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="d816b-119">In dit artikel wordt uitgelegd hoe u gebruikerslabels configureert in & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d816b-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="d816b-120">Er zijn geen cmdlets in & compliancecentrum om gebruikerslabels te beheren.</span><span class="sxs-lookup"><span data-stu-id="d816b-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="d816b-121">Zie Beveiligingsaanbevelingen voor [prioriteitsaccounts in](security-recommendations-for-priority-accounts.md)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d816b-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d816b-122">Als u het geïntegreerde beveiligingscentrum Microsoft 365, kunt u hier tags instellen: https://security.microsoft.com/securitysettings/userTags .</span><span class="sxs-lookup"><span data-stu-id="d816b-122">If you use the unified Microsoft 365 security center, you can set tags here: https://security.microsoft.com/securitysettings/userTags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d816b-123">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d816b-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d816b-124">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d816b-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d816b-125">Als u rechtstreeks naar de pagina **Gebruikerslabels wilt** gaan, opent u <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="d816b-125">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="d816b-126">Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="d816b-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d816b-127">Als u gebruikerslabels wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="d816b-127">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d816b-128">Als u leden wilt toevoegen en verwijderen uit bestaande gebruikerslabels, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of Beveiligingsoperator </span><span class="sxs-lookup"><span data-stu-id="d816b-128">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="d816b-129">Voor alleen-lezen toegang tot gebruikerslabels moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="d816b-129">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d816b-130">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d816b-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="d816b-131">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d816b-131">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d816b-132">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d816b-132">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="d816b-133">Gebruikerslabelbeheer wordt beheerd door de rollen **Tag Reader** en **Tag Manager.**</span><span class="sxs-lookup"><span data-stu-id="d816b-133">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="d816b-134">U kunt ook prioriteitsaccounts beheren en controleren in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d816b-134">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d816b-135">Zie Prioriteitsaccounts beheren [en controleren voor instructies.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="d816b-135">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="d816b-136">Zie dit onderwerp voor informatie over het _beveiligen_ van bevoorrechte accounts [(beheerdersaccounts).](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="d816b-136">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="d816b-137">Het beveiligings- & compliancecentrum gebruiken om gebruikerslabels te maken</span><span class="sxs-lookup"><span data-stu-id="d816b-137">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="d816b-138">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="d816b-138">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d816b-139">Klik op **de pagina Gebruikerslabels** die wordt geopend op **Tag maken.**</span><span class="sxs-lookup"><span data-stu-id="d816b-139">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="d816b-140">De **wizard Tag maken** wordt geopend in een nieuwe fly-out. Configureer **op de pagina Label** definiëren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d816b-140">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="d816b-141">**Naam:** Voer een unieke, beschrijvende naam in voor de tag.</span><span class="sxs-lookup"><span data-stu-id="d816b-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="d816b-142">Dit is de waarde die u ziet en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d816b-142">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="d816b-143">**Beschrijving:** Voer een optionele beschrijving voor de tag in.</span><span class="sxs-lookup"><span data-stu-id="d816b-143">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="d816b-144">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d816b-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d816b-145">Ga op **de pagina Gebruikers toewijzen** naar een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d816b-145">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="d816b-146">Klik **op Gebruikers toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d816b-146">Click **Add users**.</span></span> <span data-ttu-id="d816b-147">Ga als volgt te werk om afzonderlijke gebruikers of groepen toe te voegen in de fly-out die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d816b-147">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="d816b-148">Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d816b-148">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="d816b-149">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.</span><span class="sxs-lookup"><span data-stu-id="d816b-149">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="d816b-150">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="d816b-150">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="d816b-151">Als u afzonderlijke items uit het vak wilt verwijderen, klikt u op **Pictogram** ![ Verwijderen verwijderen van de gebruiker of groep in het ](../../media/scc-remove-icon.png) vak.</span><span class="sxs-lookup"><span data-stu-id="d816b-151">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="d816b-152">Als u bestaande items wilt verwijderen uit de lijst onder het vak, klikt u **op Pictogram** Verwijderen van ![ de ](../../media/scc-remove-icon.png) vermelding.</span><span class="sxs-lookup"><span data-stu-id="d816b-152">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="d816b-153">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d816b-153">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="d816b-154">Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="d816b-154">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="d816b-155">Zorg ervoor dat het tekstbestand één invoer per regel bevat.</span><span class="sxs-lookup"><span data-stu-id="d816b-155">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="d816b-156">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d816b-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d816b-157">Controleer op **de pagina Tag** controleren uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="d816b-157">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="d816b-158">U kunt in **de specifieke** sectie op Bewerken klikken om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="d816b-158">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="d816b-159">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="d816b-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="d816b-160">Het beveiligings- & compliancecentrum gebruiken om gebruikerslabels weer te geven</span><span class="sxs-lookup"><span data-stu-id="d816b-160">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="d816b-161">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="d816b-161">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d816b-162">Selecteer op **de pagina Gebruikerslabels** die wordt geopend de gebruikerstag die u wilt weergeven (klik niet op het selectievakje).</span><span class="sxs-lookup"><span data-stu-id="d816b-162">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="d816b-163">Bekijk de instellingen in de alleen-lezen details die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d816b-163">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="d816b-164">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d816b-164">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="d816b-165">Gebruik het beveiligings- & compliancecentrum om gebruikerslabels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d816b-165">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="d816b-166">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="d816b-166">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d816b-167">Selecteer op **de pagina Gebruikerslabels** die wordt geopend de gebruikerstag die u wilt weergeven en klik vervolgens op **Tag bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d816b-167">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="d816b-168">De wizard Beleid wordt geopend in **een fly-out tag** bewerken. Klik **op Volgende** om de instellingen te bekijken en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d816b-168">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="d816b-169">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="d816b-169">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="d816b-170">Gebruik het beveiligings- & compliancecentrum om gebruikerslabels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d816b-170">Use the Security & Compliance Center to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="d816b-171">U kunt de ingebouwde tag **Priority-account niet** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d816b-171">You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="d816b-172">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="d816b-172">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d816b-173">Selecteer op **de pagina** Gebruikerslabels die wordt geopend de gebruikerstag die u wilt verwijderen, klik op **Tag** verwijderen en selecteer vervolgens **Ja,** verwijderen in de waarschuwing die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d816b-173">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
