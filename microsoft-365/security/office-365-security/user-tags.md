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
description: Beheerders kunnen leren hoe u specifieke groepen gebruikers kunt identificeren met gebruikerslabels in Microsoft Defender voor Office 365-abonnement 2. Tagfiltering is beschikbaar in waarschuwingen, rapporten en onderzoeken in Microsoft Defender voor Office 365 om snel de gelabelde gebruikers te identificeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2c1dc426bae77cd35b567bf166032855327a8ffe
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943009"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f25ae-104">Gebruikerslabels in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f25ae-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="f25ae-105">De functie gebruikerslabels is beschikbaar in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f25ae-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="f25ae-106">Voor meer informatie over de releaseplanning raadpleegt u de [routekaart voor Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="f25ae-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="f25ae-107">Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f25ae-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="f25ae-108">Er zijn twee typen gebruikerslabels:</span><span class="sxs-lookup"><span data-stu-id="f25ae-108">There are two types of user tags:</span></span>

- <span data-ttu-id="f25ae-109">**Systeemlabels:** Momenteel is [Prioriteitsaccounts](../../admin/setup/priority-accounts.md) het enige type systeemlabel.</span><span class="sxs-lookup"><span data-stu-id="f25ae-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="f25ae-110">**Aangepaste tags:** u maakt deze gebruikerslabels zelf.</span><span class="sxs-lookup"><span data-stu-id="f25ae-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="f25ae-111">Als uw organisatie Defender voor Office 365-abonnement 2 heeft (inbegrepen in uw abonnement of als invoegvoeggebruik), kunt u aangepaste gebruikerslabels maken naast het gebruik van de tag prioriteitsaccounts.</span><span class="sxs-lookup"><span data-stu-id="f25ae-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="f25ae-112">Momenteel kunt u alleen gebruikerslabels toepassen op postvakgebruikers.</span><span class="sxs-lookup"><span data-stu-id="f25ae-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="f25ae-113">Nadat u systeemlabels of aangepaste tags op gebruikers hebt toegepast, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:</span><span class="sxs-lookup"><span data-stu-id="f25ae-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="f25ae-114">Waarschuwingen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="f25ae-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="f25ae-115">Threat Explorer en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="f25ae-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="f25ae-116">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="f25ae-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="f25ae-117">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="f25ae-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="f25ae-118">Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) gebruiken in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="f25ae-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="f25ae-119">In dit artikel wordt uitgelegd hoe u gebruikerslabels configureert in & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="f25ae-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="f25ae-120">Er zijn geen cmdlets in & compliancecentrum om gebruikerslabels te beheren.</span><span class="sxs-lookup"><span data-stu-id="f25ae-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="f25ae-121">Zie Beveiligingsaanbevelingen voor [prioriteitsaccounts in Microsoft 365](security-recommendations-for-priority-accounts.md)als u wilt zien hoe gebruikerslabels deel uitmaken van de strategie voor het beschermen van gebruikersaccounts met een hoge impact.</span><span class="sxs-lookup"><span data-stu-id="f25ae-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f25ae-122">Als u het geïntegreerde Microsoft 365-beveiligingscentrum gebruikt, kunt u hier tags instellen: https://security.microsoft.com/userTags .</span><span class="sxs-lookup"><span data-stu-id="f25ae-122">If you use the unified Microsoft 365 security center, you can set tags here: https://security.microsoft.com/userTags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f25ae-123">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f25ae-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f25ae-124">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f25ae-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f25ae-125">Als u rechtstreeks naar de pagina **Gebruikerslabels wilt** gaan, opent u <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="f25ae-125">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="f25ae-126">Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="f25ae-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f25ae-127">Als u gebruikerslabels wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="f25ae-127">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f25ae-128">Als u leden wilt toevoegen en verwijderen uit bestaande gebruikerslabels, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of Beveiligingsoperator </span><span class="sxs-lookup"><span data-stu-id="f25ae-128">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="f25ae-129">Voor alleen-lezen toegang tot gebruikerslabels moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-129">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f25ae-130">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f25ae-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="f25ae-131">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="f25ae-131">**Notes**:</span></span>

  - <span data-ttu-id="f25ae-132">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f25ae-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f25ae-133">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f25ae-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="f25ae-134">Gebruikerslabelbeheer wordt beheerd door de rollen **Tag Reader** en **Tag Manager.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="f25ae-135">U kunt ook prioriteitsaccounts beheren en controleren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f25ae-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f25ae-136">Zie Prioriteitsaccounts beheren [en controleren voor instructies.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="f25ae-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="f25ae-137">Zie dit onderwerp voor informatie over het _beveiligen_ van bevoorrechte accounts [(beheerdersaccounts).](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="f25ae-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="f25ae-138">Het beveiligings- & compliancecentrum gebruiken om gebruikerslabels te maken</span><span class="sxs-lookup"><span data-stu-id="f25ae-138">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="f25ae-139">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-139">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f25ae-140">Klik op **de pagina Gebruikerslabels** die wordt geopend op **Tag maken.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-140">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="f25ae-141">De **wizard Tag maken** wordt geopend in een nieuwe fly-out. Configureer **op de pagina Label** definiëren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="f25ae-141">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="f25ae-142">**Naam:** Voer een unieke, beschrijvende naam in voor de tag.</span><span class="sxs-lookup"><span data-stu-id="f25ae-142">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="f25ae-143">Dit is de waarde die u ziet en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f25ae-143">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="f25ae-144">**Beschrijving:** Voer een optionele beschrijving voor de tag in.</span><span class="sxs-lookup"><span data-stu-id="f25ae-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="f25ae-145">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f25ae-146">Ga op **de pagina Gebruikers toewijzen** naar een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="f25ae-146">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="f25ae-147">Klik **op Gebruikers toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-147">Click **Add users**.</span></span> <span data-ttu-id="f25ae-148">Ga als volgt te werk om afzonderlijke gebruikers of groepen toe te voegen in de fly-out die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f25ae-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="f25ae-149">Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f25ae-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="f25ae-150">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.</span><span class="sxs-lookup"><span data-stu-id="f25ae-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="f25ae-151">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="f25ae-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="f25ae-152">Als u afzonderlijke items uit het vak wilt verwijderen, klikt u op **Pictogram** ![ Verwijderen verwijderen van de gebruiker of groep in het ](../../media/scc-remove-icon.png) vak.</span><span class="sxs-lookup"><span data-stu-id="f25ae-152">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="f25ae-153">Als u bestaande items wilt verwijderen uit de lijst onder het vak, klikt u **op Pictogram** Verwijderen van ![ de ](../../media/scc-remove-icon.png) vermelding.</span><span class="sxs-lookup"><span data-stu-id="f25ae-153">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="f25ae-154">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-154">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="f25ae-155">Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="f25ae-155">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="f25ae-156">Zorg ervoor dat het tekstbestand één invoer per regel bevat.</span><span class="sxs-lookup"><span data-stu-id="f25ae-156">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="f25ae-157">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-157">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f25ae-158">Controleer op **de pagina Tag** controleren uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="f25ae-158">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="f25ae-159">U kunt in **de specifieke** sectie op Bewerken klikken om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="f25ae-159">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="f25ae-160">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="f25ae-161">Het beveiligings- & compliancecentrum gebruiken om gebruikerslabels weer te geven</span><span class="sxs-lookup"><span data-stu-id="f25ae-161">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="f25ae-162">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-162">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f25ae-163">Selecteer op **de pagina Gebruikerslabels** die wordt geopend de gebruikerstag die u wilt weergeven (klik niet op het selectievakje).</span><span class="sxs-lookup"><span data-stu-id="f25ae-163">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="f25ae-164">Bekijk de instellingen in de alleen-lezen details die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f25ae-164">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="f25ae-165">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="f25ae-165">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="f25ae-166">Gebruik het beveiligings- & compliancecentrum om gebruikerslabels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="f25ae-166">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="f25ae-167">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-167">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f25ae-168">Selecteer op **de pagina Gebruikerslabels** die wordt geopend de gebruikerstag die u wilt weergeven en klik vervolgens op **Tag bewerken.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-168">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="f25ae-169">De wizard Beleid wordt geopend in **een fly-out tag** bewerken. Klik **op Volgende** om de instellingen te bekijken en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f25ae-169">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="f25ae-170">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-170">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="f25ae-171">Gebruik het beveiligings- & compliancecentrum om gebruikerslabels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="f25ae-171">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="f25ae-172">**Opmerking:** U kunt de ingebouwde tag **Priority-account niet** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f25ae-172">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="f25ae-173">Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="f25ae-173">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="f25ae-174">Selecteer op **de pagina** Gebruikerslabels die wordt geopend de gebruikerstag die u wilt verwijderen, klik op **Tag** verwijderen en selecteer vervolgens **Ja,** verwijderen in de waarschuwing die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f25ae-174">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>