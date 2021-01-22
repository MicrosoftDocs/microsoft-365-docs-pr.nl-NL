---
title: Gebruikerslabels in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen in Microsoft Defender voor Office 365 Abonnement 2 specifieke groepen gebruikers identificeren met gebruikerslabels. Filteren van tags is beschikbaar voor waarschuwingen, rapporten en onderzoeken in Microsoft Defender voor Office 365 om snel de gelabelde gebruikers te identificeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931432"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="436b4-104">Gebruikerslabels in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="436b4-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="436b4-105">De functie voor gebruikerstags is beschikbaar in het voorbeeldvenster, is niet voor iedereen beschikbaar en kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="436b4-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="436b4-106">Bekijk de routekaart voor [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)voor informatie over het releaseschema.</span><span class="sxs-lookup"><span data-stu-id="436b4-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="436b4-107">Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="436b4-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="436b4-108">Er zijn twee typen gebruikerstags:</span><span class="sxs-lookup"><span data-stu-id="436b4-108">There are two types of user tags:</span></span>

- <span data-ttu-id="436b4-109">**Systeemlabels:** Op dit moment is [Prioriteit-accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) het enige type systeemcode.</span><span class="sxs-lookup"><span data-stu-id="436b4-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="436b4-110">**Aangepaste tags:** u maakt deze gebruikerstags zelf.</span><span class="sxs-lookup"><span data-stu-id="436b4-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="436b4-111">Als uw organisatie beschikt over Defender voor Office 365 Abonnement 2 (inbegrepen in uw abonnement of als een invoegcode), kunt u niet alleen de tag voor prioriteitsaccounts gebruiken, maar ook aangepaste gebruikerstags maken.</span><span class="sxs-lookup"><span data-stu-id="436b4-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="436b4-112">Nadat u systeemcodes of aangepaste tags hebt toegepast op gebruikers, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:</span><span class="sxs-lookup"><span data-stu-id="436b4-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="436b4-113">Waarschuwingen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="436b4-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="436b4-114">Bedreigingsverkenner en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="436b4-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="436b4-115">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="436b4-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="436b4-116">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="436b4-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="436b4-117">Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in het Exchange-beheercentrum (EAC) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="436b4-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="436b4-118">In dit artikel wordt uitgelegd hoe u gebruikerstags configureert in het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="436b4-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="436b4-119">Er zijn geen cmdlets in & compliancecentrum voor het beheren van gebruikerslabels.</span><span class="sxs-lookup"><span data-stu-id="436b4-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="436b4-120">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="436b4-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="436b4-121">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="436b4-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="436b4-122">Als u rechtstreeks naar de pagina **Gebruikerstags wilt** gaan, opent u <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="436b4-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="436b4-123">Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="436b4-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="436b4-124">Als u gebruikerstags wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="436b4-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="436b4-125">Als u leden aan bestaande gebruikerstags wilt toevoegen of eruit  **wilt** verwijderen, moet u lid zijn van de rollengroepen Organisatiebeheer, Beveiligingsbeheerder of Beveiligingsoperator.</span><span class="sxs-lookup"><span data-stu-id="436b4-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="436b4-126">Voor alleen-lezen toegang tot gebruikerstags moet u  lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="436b4-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="436b4-127">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="436b4-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="436b4-128">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="436b4-128">**Notes**:</span></span>

  - <span data-ttu-id="436b4-129">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="436b4-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="436b4-130">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="436b4-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="436b4-131">Het beheer van gebruikerstags wordt beheerd door de rollen **Taglezer,** **Tag-medewerker** en **Tagbeheer.**</span><span class="sxs-lookup"><span data-stu-id="436b4-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="436b4-132">U kunt ook prioriteitsaccounts beheren en controleren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="436b4-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="436b4-133">Zie Accounts met prioriteit [beheren en controleren voor instructies.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="436b4-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="436b4-134">Het beveiligingscentrum gebruiken om gebruikerstags te maken</span><span class="sxs-lookup"><span data-stu-id="436b4-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="436b4-135">Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="436b4-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="436b4-136">Klik op **de pagina Gebruikerstags** die wordt geopend op **Tag maken.**</span><span class="sxs-lookup"><span data-stu-id="436b4-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="436b4-137">De **wizard Label** maken wordt geopend in een nieuwe fly-out. Configureer **de volgende instellingen** op de pagina Label definiëren:</span><span class="sxs-lookup"><span data-stu-id="436b4-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="436b4-138">**Naam:** voer een unieke, beschrijvende naam voor de tag in.</span><span class="sxs-lookup"><span data-stu-id="436b4-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="436b4-139">Dit is de waarde die u ziet en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="436b4-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="436b4-140">**Beschrijving:** voer een optionele beschrijving voor de tag in.</span><span class="sxs-lookup"><span data-stu-id="436b4-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="436b4-141">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="436b4-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="436b4-142">Ga op **de pagina Gebruikers** toewijzen op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="436b4-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="436b4-143">Klik **op Gebruikers toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="436b4-143">Click **Add users**.</span></span> <span data-ttu-id="436b4-144">In het fly-out dat verschijnt, gaat u op een van de volgende stappen te werk om afzonderlijke gebruikers of groepen toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="436b4-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="436b4-145">Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="436b4-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="436b4-146">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.</span><span class="sxs-lookup"><span data-stu-id="436b4-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="436b4-147">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="436b4-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="436b4-148">Als u afzonderlijke items uit het vak wilt verwijderen, klikt u op **het** pictogram Verwijderen voor de gebruiker of ![ groep in het ](../../media/scc-remove-icon.png) vak.</span><span class="sxs-lookup"><span data-stu-id="436b4-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="436b4-149">Als u bestaande items wilt verwijderen uit de lijst onder het vak, klikt u op **het** pictogram ![ Verwijderen van de ](../../media/scc-remove-icon.png) vermelding.</span><span class="sxs-lookup"><span data-stu-id="436b4-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="436b4-150">Klik op Toevoegen wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="436b4-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="436b4-151">Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="436b4-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="436b4-152">Zorg ervoor dat het tekstbestand één vermelding per regel bevat.</span><span class="sxs-lookup"><span data-stu-id="436b4-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="436b4-153">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="436b4-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="436b4-154">Controleer de **instellingen op de** tagpagina Controleren.</span><span class="sxs-lookup"><span data-stu-id="436b4-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="436b4-155">U kunt in **de specifieke** sectie op Bewerken klikken om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="436b4-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="436b4-156">Klik op Verzenden wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="436b4-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="436b4-157">Gebruikerstags bekijken via het beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="436b4-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="436b4-158">Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="436b4-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="436b4-159">Selecteer op **de pagina Gebruikerstags** die wordt geopend, de gebruikerstag die u wilt weergeven (klik niet op het selectievakje).</span><span class="sxs-lookup"><span data-stu-id="436b4-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="436b4-160">Bekijk de instellingen in de alleen-lezen details die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="436b4-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="436b4-161">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="436b4-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="436b4-162">Het beveiligingscentrum gebruiken om gebruikerstags te wijzigen</span><span class="sxs-lookup"><span data-stu-id="436b4-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="436b4-163">Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="436b4-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="436b4-164">Selecteer op **de pagina Gebruikerstags** die wordt geopend, de gebruikerstag die u wilt bekijken en klik vervolgens op **Tag bewerken.**</span><span class="sxs-lookup"><span data-stu-id="436b4-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="436b4-165">De wizard Beleid wordt geopend in **een fly-out label** bewerken. Klik **op Volgende** om de instellingen te controleren en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="436b4-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="436b4-166">Klik op Verzenden wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="436b4-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="436b4-167">Het beveiligingscentrum gebruiken om gebruikerstags te verwijderen</span><span class="sxs-lookup"><span data-stu-id="436b4-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="436b4-168">**Opmerking:** u kunt de ingebouwde tag van het **Priority-account niet** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="436b4-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="436b4-169">Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="436b4-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="436b4-170">Selecteer op **de** pagina gebruikerstags die wordt geopend, de gebruikerstag die u wilt verwijderen, klik op Tag verwijderen en selecteer vervolgens **Ja,** verwijderen in de waarschuwing die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="436b4-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
