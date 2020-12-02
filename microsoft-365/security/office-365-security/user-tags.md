---
title: Gebruikers Tags in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze bepaalde groepen gebruikers identificeren met gebruikers Tags in Microsoft Defender voor Office 365, abonnement 2. Het filteren van labels is beschikbaar via waarschuwingen, rapporten en onderzoek in Microsoft Defender voor Office 365, zodat u snel de gecodeerde gebruikers kunt identificeren.
ms.openlocfilehash: 136de95addae7dcd48de2c6ac1f30ce67714817c
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552017"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="45a4a-104">Gebruikers Tags in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="45a4a-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="45a4a-105">De functie gebruikers Tags is in voorbeeld, is niet beschikbaar voor iedereen, en kan veranderen.</span><span class="sxs-lookup"><span data-stu-id="45a4a-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="45a4a-106">Voor informatie over de release planning raadpleegt u het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="45a4a-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="45a4a-107">Gebruikers Tags zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="45a4a-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="45a4a-108">Er zijn twee soorten gebruikers Tags:</span><span class="sxs-lookup"><span data-stu-id="45a4a-108">There are two types of user tags:</span></span>

- <span data-ttu-id="45a4a-109">**Systeem Tags**: momenteel is de [prioriteit accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) het enige type systeemcode.</span><span class="sxs-lookup"><span data-stu-id="45a4a-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="45a4a-110">**Aangepaste tags**: u kunt deze gebruikers Tags zelf maken.</span><span class="sxs-lookup"><span data-stu-id="45a4a-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="45a4a-111">Als uw organisatie is aangemeld voor Office 365, abonnement 2 (opgenomen in uw abonnement of als een invoegtoepassing), kunt u ook aangepaste gebruikers Tags maken en de tag met de prioriteits accounts gebruiken.</span><span class="sxs-lookup"><span data-stu-id="45a4a-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="45a4a-112">Wanneer u systeem Tags of aangepaste tags op gebruikers hebt toegepast, kunt u deze codes gebruiken als filters in waarschuwingen, rapporten en onderzoek:</span><span class="sxs-lookup"><span data-stu-id="45a4a-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="45a4a-113">Waarschuwingen in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="45a4a-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="45a4a-114">Bedreigings Verkenner en real-time ontdekken</span><span class="sxs-lookup"><span data-stu-id="45a4a-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="45a4a-115">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="45a4a-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="45a4a-116">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="45a4a-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="45a4a-117">Voor prioriteits accounts kunt u het [rapport e-mail problemen met prioriteits accounts](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in het Exchange-Beheercentrum (SBV) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="45a4a-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="45a4a-118">In dit artikel wordt uitgelegd hoe u gebruikers Tags kunt configureren in de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="45a4a-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="45a4a-119">De beveiligings & bevat geen cmdlets voor het beheren van gebruikers Tags.</span><span class="sxs-lookup"><span data-stu-id="45a4a-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45a4a-120">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="45a4a-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45a4a-121">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="45a4a-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="45a4a-122">Als u rechtstreeks naar de pagina **gebruikers Tags** wilt gaan, opent u deze <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="45a4a-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="45a4a-123">Als u **aangepaste gebruikers Tags** wilt maken, wijzigen of verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="45a4a-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="45a4a-124">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="45a4a-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="45a4a-125">U moet een [globale beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) of een [Exchange-beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)zijn als u prioriteit accounts (systeem Tags) wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="45a4a-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="45a4a-126">U kunt prioriteit accounts ook beheren en controleren in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="45a4a-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="45a4a-127">Zie [prioriteit accounts beheren en controleren](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="45a4a-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="45a4a-128">Beveiligingscentrum gebruiken om gebruikers Tags te maken</span><span class="sxs-lookup"><span data-stu-id="45a4a-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="45a4a-129">Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="45a4a-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="45a4a-130">Klik op de pagina **gebruikers Tags** die wordt geopend op **tag maken**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="45a4a-131">De wizard **tag maken** wordt geopend in een nieuwe vlucht. Configureer de volgende instellingen op de pagina **tag definiëren** :</span><span class="sxs-lookup"><span data-stu-id="45a4a-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="45a4a-132">**Naam**: Typ een unieke, beschrijvende naam voor de tag.</span><span class="sxs-lookup"><span data-stu-id="45a4a-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="45a4a-133">Dit is de waarde die u ziet en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="45a4a-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="45a4a-134">**Beschrijving**: Typ een optionele beschrijving voor de tag.</span><span class="sxs-lookup"><span data-stu-id="45a4a-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="45a4a-135">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="45a4a-136">Voer op de pagina **gebruikers toewijzen** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="45a4a-136">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="45a4a-137">Klik op **gebruikers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-137">Click **Add users**.</span></span> <span data-ttu-id="45a4a-138">Voer een van de volgende stappen uit om afzonderlijke gebruikers of groepen toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="45a4a-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="45a4a-139">Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="45a4a-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="45a4a-140">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.</span><span class="sxs-lookup"><span data-stu-id="45a4a-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="45a4a-141">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="45a4a-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="45a4a-142">Als u afzonderlijke vermeldingen uit het vak **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker of groep in het vak.</span><span class="sxs-lookup"><span data-stu-id="45a4a-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="45a4a-143">Als u bestaande items uit de lijst onder het vak wilt verwijderen **, klikt u** op ![ het pictogram verwijderen verwijderen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="45a4a-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="45a4a-144">Wanneer u klaar bent, klikt u op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="45a4a-145">Klik op **importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="45a4a-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="45a4a-146">Let op: het tekstbestand bevat één item per regel.</span><span class="sxs-lookup"><span data-stu-id="45a4a-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="45a4a-147">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="45a4a-148">Controleer de instellingen op de pagina **controle-label** .</span><span class="sxs-lookup"><span data-stu-id="45a4a-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="45a4a-149">U kunt klikken op **bewerken** in de sectie specifiek om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="45a4a-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="45a4a-150">Als u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="45a4a-151">Beveiligingscentrum gebruiken om gebruikers Tags weer te geven</span><span class="sxs-lookup"><span data-stu-id="45a4a-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="45a4a-152">Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="45a4a-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="45a4a-153">Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt weergeven (Klik op het selectievakje niet).</span><span class="sxs-lookup"><span data-stu-id="45a4a-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="45a4a-154">Controleer de instellingen in de alleen-lezen gegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="45a4a-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="45a4a-155">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="45a4a-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="45a4a-156">Beveiligingscentrum gebruiken om gebruikers Tags te wijzigen</span><span class="sxs-lookup"><span data-stu-id="45a4a-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="45a4a-157">Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="45a4a-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="45a4a-158">Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt weergeven en klik vervolgens op **code bewerken**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="45a4a-159">De wizard beleid wordt geopend in een **code bewerken** . Klik op **volgende** om de instellingen te bekijken en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="45a4a-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="45a4a-160">Als u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="45a4a-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="45a4a-161">Beveiligingscentrum gebruiken om gebruikers Tags te verwijderen</span><span class="sxs-lookup"><span data-stu-id="45a4a-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="45a4a-162">**Opmerking**: u kunt de code van het ingebouwde **prioriteits account** niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="45a4a-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="45a4a-163">Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="45a4a-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="45a4a-164">Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt verwijderen, klik op **markering verwijderen** en selecteer vervolgens **Ja, verwijderen** in de waarschuwing die verschijnt.</span><span class="sxs-lookup"><span data-stu-id="45a4a-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
