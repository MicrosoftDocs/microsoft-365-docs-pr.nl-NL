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
ms.openlocfilehash: 105e927e50f7b1d1217587587b8d7ee3b7d6bd4c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904102"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3d47b-104">Gebruikerslabels in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3d47b-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="3d47b-105">De functie gebruikerslabels is beschikbaar in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="3d47b-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="3d47b-106">Voor meer informatie over de releaseplanning raadpleegt u [de Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="3d47b-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="3d47b-107">Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3d47b-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="3d47b-108">Er zijn twee typen gebruikerslabels:</span><span class="sxs-lookup"><span data-stu-id="3d47b-108">There are two types of user tags:</span></span>

- <span data-ttu-id="3d47b-109">**Systeemlabels:** Momenteel is [Prioriteitsaccounts](../../admin/setup/priority-accounts.md) het enige type systeemlabel.</span><span class="sxs-lookup"><span data-stu-id="3d47b-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="3d47b-110">**Aangepaste tags:** u maakt deze gebruikerslabels zelf.</span><span class="sxs-lookup"><span data-stu-id="3d47b-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="3d47b-111">Als uw organisatie Defender voor Office 365 abonnement 2 (inbegrepen in uw abonnement of als een invoegvoeggebruik) heeft, kunt u naast het gebruik van de tag prioriteitsaccounts ook aangepaste gebruikerslabels maken.</span><span class="sxs-lookup"><span data-stu-id="3d47b-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="3d47b-112">Momenteel kunt u alleen gebruikerslabels toepassen op postvakgebruikers.</span><span class="sxs-lookup"><span data-stu-id="3d47b-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="3d47b-113">Nadat u systeemlabels of aangepaste tags op gebruikers hebt toegepast, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:</span><span class="sxs-lookup"><span data-stu-id="3d47b-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="3d47b-114">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="3d47b-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="3d47b-115">Aangepast waarschuwingsbeleid</span><span class="sxs-lookup"><span data-stu-id="3d47b-115">Custom alert policies</span></span>](../../compliance/alert-policies.md#viewing-alerts)
- [<span data-ttu-id="3d47b-116">Threat Explorer en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="3d47b-116">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="3d47b-117">Entiteitspagina van e-mail</span><span class="sxs-lookup"><span data-stu-id="3d47b-117">Email entity page</span></span>](mdo-email-entity-page.md#other-innovations)
- [<span data-ttu-id="3d47b-118">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="3d47b-118">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="3d47b-119">Campagneweergaven</span><span class="sxs-lookup"><span data-stu-id="3d47b-119">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="3d47b-120">Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) gebruiken in Exchange beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="3d47b-120">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="3d47b-121">In dit artikel wordt uitgelegd hoe u gebruikerslabels configureert in Microsoft 365 Defender-portal.</span><span class="sxs-lookup"><span data-stu-id="3d47b-121">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="3d47b-122">Er zijn geen cmdlets in Microsoft 365 Defender-portal om gebruikerslabels te beheren.</span><span class="sxs-lookup"><span data-stu-id="3d47b-122">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="3d47b-123">Zie Beveiligingsaanbevelingen voor [prioriteitsaccounts in](security-recommendations-for-priority-accounts.md)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d47b-123">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d47b-124">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="3d47b-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3d47b-125">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="3d47b-125">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="3d47b-126">Als u rechtstreeks naar de pagina **Gebruikerslabels wilt** gaan, opent u <https://security.microsoft.com/securitysettings/userTags> .</span><span class="sxs-lookup"><span data-stu-id="3d47b-126">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="3d47b-127">U moet machtigingen krijgen toegewezen in de Microsoft 365 Defender-portal voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="3d47b-127">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3d47b-128">Als u gebruikerslabels wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="3d47b-128">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3d47b-129">Als u leden wilt toevoegen en verwijderen uit bestaande gebruikerslabels, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of Beveiligingsoperator </span><span class="sxs-lookup"><span data-stu-id="3d47b-129">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="3d47b-130">Voor alleen-lezen toegang tot gebruikerslabels moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-130">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3d47b-131">Zie Machtigingen [in de portal Microsoft 365 Defender voor meer informatie.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="3d47b-131">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="3d47b-132">Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum, krijgen  gebruikers de vereiste machtigingen in de Microsoft 365 Defender-portal en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d47b-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3d47b-133">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3d47b-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="3d47b-134">Gebruikerslabelbeheer wordt beheerd door de rollen **Tag Reader** en **Tag Manager.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="3d47b-135">U kunt ook prioriteitsaccounts beheren en controleren in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3d47b-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3d47b-136">Zie Prioriteitsaccounts beheren [en controleren voor instructies.](../../admin/setup/priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="3d47b-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="3d47b-137">Zie dit onderwerp voor informatie over het _beveiligen_ van bevoorrechte accounts [(beheerdersaccounts).](/azure/architecture/framework/security/critical-impact-accounts)</span><span class="sxs-lookup"><span data-stu-id="3d47b-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="3d47b-138">Gebruik de Microsoft 365 Defender-portal om gebruikerslabels te maken</span><span class="sxs-lookup"><span data-stu-id="3d47b-138">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="3d47b-139">Ga in Microsoft 365 Defender-portal naar **Instellingen** \> **e-mail &** \> **samenwerking Gebruikerslabels**.</span><span class="sxs-lookup"><span data-stu-id="3d47b-139">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="3d47b-140">Klik op **de pagina Gebruikerslabels** op ![ Tagpictogram maken Tag ](../../media/m365-cc-sc-create-icon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-140">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="3d47b-141">De **wizard Tag maken** wordt geopend in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="3d47b-141">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="3d47b-142">Configureer **op de pagina Label** definiëren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="3d47b-142">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="3d47b-143">**Naam:** Voer een unieke, beschrijvende naam in voor de tag.</span><span class="sxs-lookup"><span data-stu-id="3d47b-143">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="3d47b-144">Dit is de waarde die u ziet en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3d47b-144">This is the value that you'll see and use.</span></span> <span data-ttu-id="3d47b-145">Houd er rekening mee dat u de naam van een tag niet kunt wijzigen nadat u deze hebt maken.</span><span class="sxs-lookup"><span data-stu-id="3d47b-145">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="3d47b-146">**Beschrijving:** Voer een optionele beschrijving voor de tag in.</span><span class="sxs-lookup"><span data-stu-id="3d47b-146">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="3d47b-147">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3d47b-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3d47b-148">Ga op **de pagina Leden** toewijzen naar een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="3d47b-148">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="3d47b-149">Klik ![ op Pictogram Leden toevoegen Leden ](../../media/m365-cc-sc-create-icon.png) **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-149">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="3d47b-150">Ga als volgt te werk om afzonderlijke gebruikers of groepen toe te voegen in de fly-out die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="3d47b-150">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="3d47b-151">Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3d47b-151">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="3d47b-152">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.</span><span class="sxs-lookup"><span data-stu-id="3d47b-152">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="3d47b-153">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="3d47b-153">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="3d47b-154">Als u afzonderlijke items wilt verwijderen, klikt u op</span><span class="sxs-lookup"><span data-stu-id="3d47b-154">To remove individual entries, click</span></span> ![Pictogram Item verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="3d47b-156">naast het item in het vak.</span><span class="sxs-lookup"><span data-stu-id="3d47b-156">next to the entry in the box.</span></span>
     - <span data-ttu-id="3d47b-157">Als u alle items wilt verwijderen, klikt u op Invoerpictogram verwijderen in het item Geselecteerde nn-gebruikers en ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **nn-groepen** onder het vak.</span><span class="sxs-lookup"><span data-stu-id="3d47b-157">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="3d47b-158">Wanneer u klaar bent, klikt u op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-158">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="3d47b-159">Terug op de **pagina Leden toewijzen** kunt u ook items verwijderen door te klikken op Pictogram Verwijderen naast het ![ ](../../media/m365-cc-sc-delete-icon.png) item.</span><span class="sxs-lookup"><span data-stu-id="3d47b-159">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="3d47b-160">Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="3d47b-160">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="3d47b-161">Zorg ervoor dat het tekstbestand één invoer per regel bevat.</span><span class="sxs-lookup"><span data-stu-id="3d47b-161">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="3d47b-162">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3d47b-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3d47b-163">Controleer de **instellingen op** de pagina Tag controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3d47b-163">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="3d47b-164">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3d47b-164">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3d47b-165">U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.</span><span class="sxs-lookup"><span data-stu-id="3d47b-165">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="3d47b-166">Wanneer u klaar bent, klikt u op **Verzenden** en klikt u vervolgens op **Gereed.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-166">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="3d47b-167">Gebruik de Microsoft 365 Defender-portal om gebruikerslabels weer te laten zien</span><span class="sxs-lookup"><span data-stu-id="3d47b-167">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="3d47b-168">Ga in Microsoft 365 Defender-portal naar **Instellingen** \> **e-mail &** \> **samenwerking Gebruikerslabels**.</span><span class="sxs-lookup"><span data-stu-id="3d47b-168">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="3d47b-169">Op de **pagina Gebruikerslabels** worden de volgende eigenschappen weergegeven in de lijst met gebruikerslabels:</span><span class="sxs-lookup"><span data-stu-id="3d47b-169">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="3d47b-170">**Tag:** De naam van de gebruikerstag.</span><span class="sxs-lookup"><span data-stu-id="3d47b-170">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="3d47b-171">Houd er rekening mee dat dit de ingebouwde **systeemtag Priority-account** bevat.</span><span class="sxs-lookup"><span data-stu-id="3d47b-171">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="3d47b-172">**Toegepast op**: Het aantal leden</span><span class="sxs-lookup"><span data-stu-id="3d47b-172">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="3d47b-173">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="3d47b-173">**Last modified**</span></span>
   - <span data-ttu-id="3d47b-174">**Gemaakt op**</span><span class="sxs-lookup"><span data-stu-id="3d47b-174">**Created on**</span></span>

3. <span data-ttu-id="3d47b-175">Wanneer u een gebruikerslabel selecteert door op de naam te klikken, worden de details weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3d47b-175">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="3d47b-176">Gebruik de Microsoft 365 Defender-portal om gebruikerslabels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="3d47b-176">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="3d47b-177">Ga in Microsoft 365 Defender-portal naar **Instellingen** \> **e-mail &** \> **samenwerking Gebruikerslabels**.</span><span class="sxs-lookup"><span data-stu-id="3d47b-177">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="3d47b-178">Selecteer op **de pagina Gebruikerslabels** de gebruikerstag in de lijst en klik vervolgens op ![ Tagpictogram bewerken Tag ](../../media/m365-cc-sc-edit-icon.png) **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-178">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="3d47b-179">In de details flyout die wordt weergegeven, zijn dezelfde wizard en instellingen beschikbaar zoals beschreven in de portal Use [the Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) om gebruikerslabels te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3d47b-179">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="3d47b-180">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="3d47b-180">**Notes**:</span></span>

   - <span data-ttu-id="3d47b-181">De **pagina Label definiëren** is niet beschikbaar voor de ingebouwde systeemtag Priority-account, dus u kunt de naam van deze tag niet wijzigen of de beschrijving wijzigen. </span><span class="sxs-lookup"><span data-stu-id="3d47b-181">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="3d47b-182">U kunt de naam van een aangepaste tag niet wijzigen, maar u kunt de beschrijving wel wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3d47b-182">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="3d47b-183">Gebruik de Microsoft 365 Defender-portal om gebruikerslabels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="3d47b-183">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="3d47b-184">U kunt de ingebouwde systeemtag **Priority-account** niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3d47b-184">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="3d47b-185">Ga in Microsoft 365 Defender-portal naar **Instellingen** \> **e-mail &** \> **samenwerking Gebruikerslabels**.</span><span class="sxs-lookup"><span data-stu-id="3d47b-185">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="3d47b-186">Selecteer op **de pagina Gebruikerslabels** de gebruikerstag in de lijst en klik vervolgens op ![ Labelpictogram verwijderen Tag ](../../media/m365-cc-sc-delete-icon.png) **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-186">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="3d47b-187">Lees de waarschuwing in het bevestigingsdialoogvenster dat wordt weergegeven en klik op **Ja, verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="3d47b-187">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
