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
ms.openlocfilehash: ad06bf90f1ecb93d671bfcad6fad0b4f2a952cb2
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663605"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="23068-104">Gebruikers Tags in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="23068-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="23068-105">De functie gebruikers Tags is in voorbeeld, is niet beschikbaar voor iedereen, en kan veranderen.</span><span class="sxs-lookup"><span data-stu-id="23068-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="23068-106">Voor informatie over de release planning raadpleegt u het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="23068-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="23068-107">Gebruikers Tags zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="23068-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="23068-108">Er zijn twee soorten gebruikers Tags:</span><span class="sxs-lookup"><span data-stu-id="23068-108">There are two types of user tags:</span></span>

- <span data-ttu-id="23068-109">**Systeem Tags**: momenteel is de [prioriteit accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) het enige type systeemcode.</span><span class="sxs-lookup"><span data-stu-id="23068-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="23068-110">**Aangepaste tags**: u kunt deze gebruikers Tags zelf maken.</span><span class="sxs-lookup"><span data-stu-id="23068-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="23068-111">Als uw organisatie is aangemeld voor Office 365, abonnement 2 (opgenomen in uw abonnement of als een invoegtoepassing), kunt u ook aangepaste gebruikers Tags maken en de tag met de prioriteits accounts gebruiken.</span><span class="sxs-lookup"><span data-stu-id="23068-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="23068-112">Wanneer u systeem Tags of aangepaste tags op gebruikers hebt toegepast, kunt u deze codes gebruiken als filters in waarschuwingen, rapporten en onderzoek:</span><span class="sxs-lookup"><span data-stu-id="23068-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="23068-113">Waarschuwingen in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="23068-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="23068-114">Bedreigings Verkenner en real-time ontdekken</span><span class="sxs-lookup"><span data-stu-id="23068-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="23068-115">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="23068-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="23068-116">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="23068-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="23068-117">Voor prioriteits accounts kunt u het [rapport e-mail problemen met prioriteits accounts](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in het Exchange-Beheercentrum (SBV) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="23068-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="23068-118">In dit artikel wordt uitgelegd hoe u gebruikers Tags kunt configureren in de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="23068-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="23068-119">De beveiligings & bevat geen cmdlets voor het beheren van gebruikers Tags.</span><span class="sxs-lookup"><span data-stu-id="23068-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="23068-120">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="23068-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="23068-121">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="23068-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="23068-122">Als u rechtstreeks naar de pagina **gebruikers Tags** wilt gaan, opent u deze <https://protection.office.com/userTags> .</span><span class="sxs-lookup"><span data-stu-id="23068-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="23068-123">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="23068-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="23068-124">Als u gebruikers tags wilt maken, wijzigen en verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="23068-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="23068-125">Als u leden wilt toevoegen aan of verwijderen uit bestaande gebruikers Tags, moet u lid zijn van de rollen groepen **Organisatiebeheer**, **beveiliging beheerder** of **beveiligings operator** .</span><span class="sxs-lookup"><span data-stu-id="23068-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="23068-126">Voor alleen-lezen toegang tot gebruikers Tags moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="23068-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="23068-127">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="23068-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="23068-128">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="23068-128">**Notes**:</span></span>

  - <span data-ttu-id="23068-129">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23068-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="23068-130">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="23068-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="23068-131">Gebruikers labels beheren wordt bepaald door de **Label lezer**, de **Inzender** voor Tags en de functies van de **tag Manager** .</span><span class="sxs-lookup"><span data-stu-id="23068-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="23068-132">U kunt prioriteit accounts ook beheren en controleren in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="23068-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="23068-133">Zie [prioriteit accounts beheren en controleren](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="23068-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="23068-134">Beveiligingscentrum gebruiken om gebruikers Tags te maken</span><span class="sxs-lookup"><span data-stu-id="23068-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="23068-135">Ga in het Beveiligingscentrum naar  \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="23068-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="23068-136">Klik op de pagina **gebruikers Tags** die wordt geopend op **tag maken**.</span><span class="sxs-lookup"><span data-stu-id="23068-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="23068-137">De wizard **tag maken** wordt geopend in een nieuwe vlucht. Configureer de volgende instellingen op de pagina **tag definiëren** :</span><span class="sxs-lookup"><span data-stu-id="23068-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="23068-138">**Naam**: Typ een unieke, beschrijvende naam voor de tag.</span><span class="sxs-lookup"><span data-stu-id="23068-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="23068-139">Dit is de waarde die u ziet en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="23068-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="23068-140">**Beschrijving**: Typ een optionele beschrijving voor de tag.</span><span class="sxs-lookup"><span data-stu-id="23068-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="23068-141">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="23068-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="23068-142">Voer op de pagina **gebruikers toewijzen** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="23068-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="23068-143">Klik op **gebruikers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="23068-143">Click **Add users**.</span></span> <span data-ttu-id="23068-144">Voer een van de volgende stappen uit om afzonderlijke gebruikers of groepen toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="23068-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="23068-145">Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="23068-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="23068-146">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.</span><span class="sxs-lookup"><span data-stu-id="23068-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="23068-147">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="23068-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="23068-148">Als u afzonderlijke vermeldingen uit het vak **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker of groep in het vak.</span><span class="sxs-lookup"><span data-stu-id="23068-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="23068-149">Als u bestaande items uit de lijst onder het vak wilt verwijderen **, klikt u** op ![ het pictogram verwijderen verwijderen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="23068-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="23068-150">Wanneer u klaar bent, klikt u op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="23068-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="23068-151">Klik op **importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="23068-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="23068-152">Let op: het tekstbestand bevat één item per regel.</span><span class="sxs-lookup"><span data-stu-id="23068-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="23068-153">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="23068-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="23068-154">Controleer de instellingen op de pagina **controle-label** .</span><span class="sxs-lookup"><span data-stu-id="23068-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="23068-155">U kunt klikken op **bewerken** in de sectie specifiek om wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="23068-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="23068-156">Als u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="23068-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="23068-157">Beveiligingscentrum gebruiken om gebruikers Tags weer te geven</span><span class="sxs-lookup"><span data-stu-id="23068-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="23068-158">Ga in het Beveiligingscentrum naar  \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="23068-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="23068-159">Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt weergeven (Klik op het selectievakje niet).</span><span class="sxs-lookup"><span data-stu-id="23068-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="23068-160">Controleer de instellingen in de alleen-lezen gegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="23068-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="23068-161">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="23068-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="23068-162">Beveiligingscentrum gebruiken om gebruikers Tags te wijzigen</span><span class="sxs-lookup"><span data-stu-id="23068-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="23068-163">Ga in het Beveiligingscentrum naar  \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="23068-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="23068-164">Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt weergeven en klik vervolgens op **code bewerken**.</span><span class="sxs-lookup"><span data-stu-id="23068-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="23068-165">De wizard beleid wordt geopend in een **code bewerken** . Klik op **volgende** om de instellingen te bekijken en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="23068-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="23068-166">Als u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="23068-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="23068-167">Beveiligingscentrum gebruiken om gebruikers Tags te verwijderen</span><span class="sxs-lookup"><span data-stu-id="23068-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="23068-168">**Opmerking**: u kunt de code van het ingebouwde **prioriteits account** niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="23068-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="23068-169">Ga in het Beveiligingscentrum naar  \> **gebruikers Tags** van Threat Management.</span><span class="sxs-lookup"><span data-stu-id="23068-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="23068-170">Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt verwijderen, klik op **markering verwijderen** en selecteer vervolgens **Ja, verwijderen** in de waarschuwing die verschijnt.</span><span class="sxs-lookup"><span data-stu-id="23068-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
