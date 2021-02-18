---
title: Berichten en bestanden in quarantaine beheren als beheerder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over het weergeven en beheren van in quarantaine geplaatste berichten voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22bcf0cefb746e92ccadf8254f4076b47ee475c4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287783"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="d6598-104">Berichten en bestanden in quarantaine beheren als EOP-beheerder</span><span class="sxs-lookup"><span data-stu-id="d6598-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d6598-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d6598-105">**Applies to**</span></span>
- [<span data-ttu-id="d6598-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d6598-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d6598-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d6598-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d6598-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6598-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d6598-109">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="d6598-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="d6598-110">Zie In quarantaine [geplaatste e-mailberichten in EOP voor meer informatie.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="d6598-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="d6598-111">Beheerders kunnen alle typen in quarantaine geplaatste berichten voor alle gebruikers weergeven, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d6598-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="d6598-112">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, zeer vertrouwelijk phishing of als gevolg van regels voor de e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="d6598-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d6598-113">Beheerders kunnen ook fout-positieven rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6598-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="d6598-114">Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen in quarantaine geplaatste bestanden ook weergeven, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6598-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="d6598-115">U bekijkt en beheert berichten in quarantaine in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="d6598-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d6598-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d6598-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d6598-117">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="d6598-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="d6598-118">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="d6598-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="d6598-119">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6598-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d6598-120">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6598-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d6598-121">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="d6598-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d6598-122">Als u acties wilt uitvoeren op berichten in quarantaine voor alle gebruikers, moet u lid zijn van de rollengroepen Organisatiebeheer, Beveiligingsbeheerder of  <sup>\*</sup> Quarantainebeheerder.</span><span class="sxs-lookup"><span data-stu-id="d6598-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="d6598-123">Voor alleen-lezen toegang tot berichten in quarantaine voor alle gebruikers  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="d6598-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d6598-124">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d6598-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="d6598-125">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d6598-125">**Notes**:</span></span>

  - <span data-ttu-id="d6598-126">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6598-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d6598-127">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d6598-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d6598-128">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="d6598-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="d6598-129"><sup>\*</sup> Leden van de **rollengroep Quarantainebeheerder** moeten ook lid zijn van de rollengroep **Systeembeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) om quarantaineprocedures te kunnen uitvoeren in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6598-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="d6598-130">In quarantaine geplaatste berichten worden een standaardperiode bewaard voordat ze automatisch worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="d6598-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="d6598-131">30 dagen voor berichten die in quarantaine worden geplaatst door antispambeleid (spam, phishing en bulk-e-mail).</span><span class="sxs-lookup"><span data-stu-id="d6598-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="d6598-132">Dit is de standaardwaarde en de maximumwaarde.</span><span class="sxs-lookup"><span data-stu-id="d6598-132">This is the default and maximum value.</span></span> <span data-ttu-id="d6598-133">Zie Antispambeleid configureren als u deze waarde (lager) [wilt configureren.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d6598-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="d6598-134">15 dagen voor berichten die malware bevatten.</span><span class="sxs-lookup"><span data-stu-id="d6598-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="d6598-135">15 dagen voor bestanden die in quarantaine worden geplaatst door veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6598-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="d6598-136">Wanneer een bericht in quarantaine is verlopen, kunt u het niet herstellen.</span><span class="sxs-lookup"><span data-stu-id="d6598-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="d6598-137">Het beveiligings- & voor het beheren van e-mailberichten die in quarantaine zijn geplaatst</span><span class="sxs-lookup"><span data-stu-id="d6598-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="d6598-138">In quarantaine geplaatste e-mail weergeven</span><span class="sxs-lookup"><span data-stu-id="d6598-138">View quarantined email</span></span>

1. <span data-ttu-id="d6598-139">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="d6598-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="d6598-140">Controleer of **In quarantaine weergeven** is ingesteld op het standaardwaarde-e-mailbericht. </span><span class="sxs-lookup"><span data-stu-id="d6598-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="d6598-141">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="d6598-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="d6598-142">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="d6598-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d6598-143">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="d6598-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="d6598-144">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-145">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-146">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-147">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-148">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-149">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-150">**Vervalt op**</span><span class="sxs-lookup"><span data-stu-id="d6598-150">**Expires**</span></span>
   - <span data-ttu-id="d6598-151">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="d6598-151">**Recipient**</span></span>
   - <span data-ttu-id="d6598-152">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="d6598-152">**Message ID**</span></span>
   - <span data-ttu-id="d6598-153">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="d6598-153">**Policy name**</span></span>
   - <span data-ttu-id="d6598-154">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="d6598-154">**Size**</span></span>
   - <span data-ttu-id="d6598-155">**Richting**</span><span class="sxs-lookup"><span data-stu-id="d6598-155">**Direction**</span></span>

   <span data-ttu-id="d6598-156">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d6598-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="d6598-157">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="d6598-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d6598-158">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="d6598-158">The available filters are:</span></span>

   - <span data-ttu-id="d6598-159">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="d6598-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="d6598-160">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="d6598-160">**Today**</span></span>
     - <span data-ttu-id="d6598-161">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="d6598-161">**Next 2 days**</span></span>
     - <span data-ttu-id="d6598-162">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="d6598-162">**Next 7 days**</span></span>
     - <span data-ttu-id="d6598-163">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="d6598-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="d6598-164">**Ontvangen op**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="d6598-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="d6598-165">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="d6598-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="d6598-166">**Beleid:** het bericht komt overeen met de voorwaarden van een e-mailstroomregel (ook wel transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="d6598-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="d6598-167">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="d6598-167">**Bulk**</span></span>
     - <span data-ttu-id="d6598-168">**Phish:** het spamfilter was Phishing-e-mail of anti-phishingbeveiliging in quarantaine geplaatst (instellingen voor [spoofing](set-up-anti-phishing-policies.md#spoof-settings) of [imitatiebeveiliging).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) </span><span class="sxs-lookup"><span data-stu-id="d6598-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="d6598-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="d6598-169">**Malware**</span></span>
     - <span data-ttu-id="d6598-170">**Spam**</span><span class="sxs-lookup"><span data-stu-id="d6598-170">**Spam**</span></span>
     - <span data-ttu-id="d6598-171">**Phish met hoog vertrouwen**</span><span class="sxs-lookup"><span data-stu-id="d6598-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="d6598-172">**Beleidstype**: berichten filteren op beleidstype:</span><span class="sxs-lookup"><span data-stu-id="d6598-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="d6598-173">**Anti-malwarebeleid**</span><span class="sxs-lookup"><span data-stu-id="d6598-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="d6598-174">**Beleid voor veilige bijlagen**</span><span class="sxs-lookup"><span data-stu-id="d6598-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="d6598-175">**Beleid tegen phishing**</span><span class="sxs-lookup"><span data-stu-id="d6598-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="d6598-176">**Beleid voor gehoste inhoudsfilters** (antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="d6598-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="d6598-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="d6598-177">**Transport rule**</span></span>

   - <span data-ttu-id="d6598-178">**E-mailontvanger:** Alle gebruikers of alleen berichten die naar u zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="d6598-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="d6598-179">Eindgebruikers kunnen alleen in quarantaine geplaatste berichten beheren die naar hen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="d6598-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="d6598-180">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="d6598-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="d6598-181">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="d6598-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="d6598-182">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="d6598-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="d6598-183">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="d6598-183">Wildcards aren't supported.</span></span> <span data-ttu-id="d6598-184">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d6598-184">You can search by the following values:</span></span>

   - <span data-ttu-id="d6598-185">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="d6598-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="d6598-186">U hebt bericht [](message-trace-scc.md) traceren bijvoorbeeld gebruikt om te zoeken naar een bericht dat is verzonden naar een gebruiker in uw organisatie en u hebt vastgesteld dat het bericht in quarantaine is geplaatst in plaats van is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="d6598-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="d6598-187">Zorg ervoor dat u de volledige bericht-id, die hoekhaken ( ) kan bevatten, op \<\> nemen.</span><span class="sxs-lookup"><span data-stu-id="d6598-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="d6598-188">Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="d6598-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="d6598-189">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="d6598-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="d6598-190">**Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht.</span><span class="sxs-lookup"><span data-stu-id="d6598-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="d6598-191">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="d6598-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="d6598-192">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="d6598-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="d6598-193">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="d6598-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="d6598-194">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="d6598-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="d6598-195">**Beleidsnaam:** de naam van het beleid dat verantwoordelijk was voor het quarantining van het bericht.</span><span class="sxs-lookup"><span data-stu-id="d6598-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="d6598-196">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="d6598-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="d6598-197">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="d6598-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="d6598-198">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="d6598-198">View quarantined message details</span></span>

<span data-ttu-id="d6598-199">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="d6598-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d6598-200">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="d6598-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="d6598-201">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="d6598-201">**Sender address**</span></span>

- <span data-ttu-id="d6598-202">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d6598-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="d6598-203">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="d6598-203">**Subject**</span></span>

- <span data-ttu-id="d6598-204">**Reden in** quarantaine: geeft aan of een bericht is geïdentificeerd als **Spam,** **Bulk,** **Phish,** aan een regel voor de e-mailstroom **(transportregel)** of is geïdentificeerd als **malware.**</span><span class="sxs-lookup"><span data-stu-id="d6598-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="d6598-205">**Aantal geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="d6598-205">**Recipient count**</span></span>

- <span data-ttu-id="d6598-206">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="d6598-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="d6598-207">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d6598-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="d6598-208">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="d6598-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="d6598-209">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="d6598-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="d6598-210">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="d6598-210">Take action on quarantined email</span></span>

<span data-ttu-id="d6598-211">Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u wilt doen met de berichten in het deelvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="d6598-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d6598-212">**Releasebericht:** kies de volgende opties in het flyoutvenster dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d6598-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="d6598-213">**Rapporteer berichten aan Microsoft** voor analyse: Dit is standaard geselecteerd en meldt het bericht dat verkeerd in quarantaine is geplaatst bij Microsoft als fout-positief.</span><span class="sxs-lookup"><span data-stu-id="d6598-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="d6598-214">Als het bericht in quarantaine is geplaatst als spam, bulkmail, phishing of malware, wordt het bericht ook gerapporteerd aan het Microsoft-team voor spamanalyse.</span><span class="sxs-lookup"><span data-stu-id="d6598-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="d6598-215">Afhankelijk van de analyse kunnen de regels voor het filteren van spam voor de hele service zo worden aangepast dat het bericht wordt doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="d6598-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="d6598-216">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="d6598-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="d6598-217">**Berichten vrijgeven aan alle geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="d6598-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="d6598-218">**Berichten vrijgeven aan specifieke geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="d6598-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="d6598-219">**Berichten vrijgeven aan andere personen:** het vrijgeven van malware aan andere personen dan oorspronkelijke geadresseerden wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="d6598-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="d6598-220">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d6598-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="d6598-221">Opmerkingen over het vrijgeven van berichten:</span><span class="sxs-lookup"><span data-stu-id="d6598-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="d6598-222">U kunt een bericht maar één keer vrijgeven aan dezelfde geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="d6598-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="d6598-223">Alleen geadresseerden die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="d6598-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="d6598-224">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d6598-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="d6598-225">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="d6598-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="d6598-226">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="d6598-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="d6598-227">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="d6598-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="d6598-228">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="d6598-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="d6598-229">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="d6598-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="d6598-230">**Verwijderen uit quarantaine:** nadat u **in** de waarschuwing die wordt weergegeven op Ja hebt geklikt, wordt het bericht onmiddellijk verwijderd zonder dat het naar de oorspronkelijke geadresseerden wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="d6598-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="d6598-231">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="d6598-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="d6598-232">**Bericht verzenden:** kies de volgende opties in het flyoutvenster dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d6598-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="d6598-233">**Objecttype:** **E-mail** (standaard), **URL** of **Bijlage.**</span><span class="sxs-lookup"><span data-stu-id="d6598-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="d6598-234">**Inzendingsindeling:** **Netwerkbericht-id** (standaard met  de bijbehorende waarde in het vak Netwerkbericht-id) of **Bestand** (blader naar een lokaal EML- of MSG-bestand).</span><span class="sxs-lookup"><span data-stu-id="d6598-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="d6598-235">Als u Bestand **selecteert en** vervolgens Netwerkbericht-id selecteert, is de oorspronkelijke waarde verdwenen. </span><span class="sxs-lookup"><span data-stu-id="d6598-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="d6598-236">**Geadresseerden:** typ een oorspronkelijke geadresseerde van het bericht bij leasen of klik op **Alles selecteren** om alle geadresseerden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="d6598-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="d6598-237">U kunt ook op **Alles selecteren** klikken en afzonderlijke geadresseerden vervolgens selectief verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d6598-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="d6598-238">**Reden voor het indienen:** **het bericht had niet moeten zijn geblokkeerd** (standaard) of moet zijn **geblokkeerd.**</span><span class="sxs-lookup"><span data-stu-id="d6598-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="d6598-239">Klik op Verzenden wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="d6598-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="d6598-240">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="d6598-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="d6598-241">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="d6598-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="d6598-242">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d6598-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="d6598-243">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="d6598-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d6598-244">Houd rekening met het volgende scenario: john@gmail.com verzendt een bericht naar faith@contoso.com en john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6598-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="d6598-245">Gmail zet dit bericht op in twee kopieën die als phishing in Microsoft in quarantaine worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="d6598-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="d6598-246">Een beheerder publiceert beide berichten naar admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6598-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="d6598-247">Het eerste uitgebrachte bericht dat het postvak van de beheerder bereikt, wordt bezorgd.</span><span class="sxs-lookup"><span data-stu-id="d6598-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="d6598-248">Het tweede uitgebrachte bericht wordt geïdentificeerd als dubbele bezorging en wordt overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d6598-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="d6598-249">Berichten worden als duplicaten geïdentificeerd als ze dezelfde bericht-id en tijd van ontvangst hebben.</span><span class="sxs-lookup"><span data-stu-id="d6598-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="d6598-250">**Berichten verwijderen:** nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd zonder dat ze worden verzonden naar de oorspronkelijke geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="d6598-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="d6598-251">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d6598-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="d6598-252">Alleen Microsoft Defender voor Office 365: het beveiligings- & voor het beheren van in quarantaine geplaatste bestanden</span><span class="sxs-lookup"><span data-stu-id="d6598-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="d6598-253">De procedures voor bestanden in quarantaine in deze sectie zijn alleen beschikbaar voor abonnees van Microsoft Defender voor Office 365 Abonnement 1 en Abonnement 2.</span><span class="sxs-lookup"><span data-stu-id="d6598-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="d6598-254">In organisaties met Defender voor Office 365 kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6598-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="d6598-255">Zie Veilige bijlagen inschakelen voor [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)en Microsoft Teams voor meer informatie over het inschakelen van beveiliging voor deze bestanden.</span><span class="sxs-lookup"><span data-stu-id="d6598-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="d6598-256">Bestanden in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="d6598-256">View quarantined files</span></span>

1. <span data-ttu-id="d6598-257">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="d6598-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="d6598-258">Weergave **in quarantaine wijzigen** in de **waardebestanden.**</span><span class="sxs-lookup"><span data-stu-id="d6598-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="d6598-259">U kunt sorteren op een veld door te klikken op een beschikbare kolomkop.</span><span class="sxs-lookup"><span data-stu-id="d6598-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="d6598-260">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="d6598-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="d6598-261">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="d6598-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d6598-262">De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="d6598-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="d6598-263">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-264">**Locatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-265">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-266">**Bestands-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-267">**Bestandsgrootte**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-268">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-269">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d6598-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="d6598-270">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="d6598-270">**Detected by**</span></span>
   - <span data-ttu-id="d6598-271">**Gewijzigd op tijd**</span><span class="sxs-lookup"><span data-stu-id="d6598-271">**Modified by time**</span></span>

4. <span data-ttu-id="d6598-272">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="d6598-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d6598-273">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="d6598-273">The available filters are:</span></span>

   - <span data-ttu-id="d6598-274">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="d6598-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="d6598-275">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="d6598-275">**Today**</span></span>
     - <span data-ttu-id="d6598-276">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="d6598-276">**Next 2 days**</span></span>
     - <span data-ttu-id="d6598-277">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="d6598-277">**Next 7 days**</span></span>
     - <span data-ttu-id="d6598-278">Een aangepast datum-/tijdbereik.</span><span class="sxs-lookup"><span data-stu-id="d6598-278">A custom date/time range.</span></span>
   - <span data-ttu-id="d6598-279">**Tijd ontvangen**</span><span class="sxs-lookup"><span data-stu-id="d6598-279">**Received time**</span></span>
   - <span data-ttu-id="d6598-280">**Reden in quarantaine:** de enige beschikbare waarde is **Malware.**</span><span class="sxs-lookup"><span data-stu-id="d6598-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="d6598-281">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="d6598-281">**Policy type**</span></span>

<span data-ttu-id="d6598-282">Nadat u een specifiek in quarantaine geplaatst bestand hebt gevonden, selecteert u het bestand om de details ervan weer te geven en er actie op te ondernemen (bijvoorbeeld om het bericht te bekijken, los te laten, te downloaden of te verwijderen).</span><span class="sxs-lookup"><span data-stu-id="d6598-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="d6598-283">Bestandsgegevens in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="d6598-283">View quarantined file details</span></span>

<span data-ttu-id="d6598-284">Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsgegevens weergegeven in het flyoutvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="d6598-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d6598-285">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="d6598-285">**File Name**</span></span>
- <span data-ttu-id="d6598-286">**Bestands-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="d6598-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="d6598-287">**Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="d6598-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="d6598-288">**Verloopt:** de datum waarop het bestand in quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d6598-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="d6598-289">**Gedetecteerd door:** Defender voor Office 365 of de antimalware-engine van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6598-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="d6598-290">**Vrijgegeven?**</span><span class="sxs-lookup"><span data-stu-id="d6598-290">**Released?**</span></span>
- <span data-ttu-id="d6598-291">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="d6598-291">**Malware Name**</span></span>
- <span data-ttu-id="d6598-292">**Document-id:** een unieke id voor het document.</span><span class="sxs-lookup"><span data-stu-id="d6598-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="d6598-293">**Bestandsgrootte:** in kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="d6598-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="d6598-294">**Organisatie** De unieke id van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d6598-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="d6598-295">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="d6598-295">**Last modified**</span></span>
- <span data-ttu-id="d6598-296">**Gewijzigd door:** de gebruiker die het bestand het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d6598-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="d6598-297">**Secure Hash-algoritme 256-bits (SHA-256)-waarde:** U kunt deze hashwaarde gebruiken om het bestand te identificeren in andere reputatieopslag of op andere locaties in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="d6598-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="d6598-298">Actie ondernemen voor bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="d6598-298">Take action on quarantined files</span></span>

<span data-ttu-id="d6598-299">Wanneer u een bestand in de lijst selecteert, kunt u de volgende acties uitvoeren op het bestand in het deelvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="d6598-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d6598-300">**Releasebestanden:** selecteer (standaard) of deselecteer **Rapportbestanden** voor analyse bij Microsoft en klik op **Bestanden vrijgeven.**</span><span class="sxs-lookup"><span data-stu-id="d6598-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="d6598-301">**Bestand downloaden**</span><span class="sxs-lookup"><span data-stu-id="d6598-301">**Download file**</span></span>
- <span data-ttu-id="d6598-302">**Bestand uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="d6598-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="d6598-303">Als u de bestanden niet los laat of verwijdert, worden ze verwijderd nadat de standaardbewaringsperiode voor quarantaine is verstreken.</span><span class="sxs-lookup"><span data-stu-id="d6598-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="d6598-304">Acties voor meerdere bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="d6598-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="d6598-305">Wanneer u meerdere in quarantaine geplaatste bestanden in de  lijst selecteert (maximaal 100), wordt het flyoutvenster Bulkacties weergegeven waarin u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d6598-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="d6598-306">**Releasebestanden**</span><span class="sxs-lookup"><span data-stu-id="d6598-306">**Release files**</span></span>
- <span data-ttu-id="d6598-307">**Bestanden verwijderen:** nadat u **in** de waarschuwing die wordt weergegeven op Ja hebt geklikt, worden de bestanden onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d6598-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="d6598-308">Exchange Online PowerShell of een zelfstandige EOP PowerShell gebruiken om in quarantaine geplaatste berichten en bestanden weer te geven en te beheren</span><span class="sxs-lookup"><span data-stu-id="d6598-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="d6598-309">De cmdlets die u gebruikt voor het weergeven en beheren van berichten en bestanden in quarantaine zijn:</span><span class="sxs-lookup"><span data-stu-id="d6598-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="d6598-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d6598-310">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="d6598-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d6598-311">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="d6598-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d6598-312">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="d6598-313">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)deze cmdlet is alleen voor berichten, niet voor malwarebestanden van veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6598-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="d6598-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d6598-314">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
