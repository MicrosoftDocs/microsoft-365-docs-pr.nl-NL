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
description: Beheerders kunnen informatie krijgen over het weergeven en beheren van berichten in quarantaine voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5e2d6a3729a24766652d4c7c0973c63b1dcb207
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272202"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="67d23-104">Berichten en bestanden in quarantaine beheren als EOP-beheerder</span><span class="sxs-lookup"><span data-stu-id="67d23-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="67d23-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="67d23-105">**Applies to**</span></span>
- [<span data-ttu-id="67d23-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="67d23-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="67d23-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="67d23-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67d23-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67d23-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="67d23-109">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="67d23-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="67d23-110">Zie In quarantaine geplaatste [e-mailberichten in EOP](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="67d23-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="67d23-111">Beheerders kunnen alle typen in quarantaine geplaatste berichten voor alle gebruikers weergeven, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="67d23-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="67d23-112">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met veel vertrouwen of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="67d23-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="67d23-113">Beheerders kunnen ook fout-positieven melden bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67d23-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="67d23-114">Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden weergeven, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67d23-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="67d23-115">U bekijkt en beheert in quarantaine geplaatste berichten in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="67d23-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67d23-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="67d23-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67d23-117">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="67d23-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="67d23-118">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="67d23-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="67d23-119">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67d23-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="67d23-120">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67d23-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="67d23-121">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="67d23-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="67d23-122">Als u actie wilt ondernemen voor berichten in quarantaine voor alle gebruikers, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of **Quarantainebeheerder.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="67d23-123">Voor alleen-lezen toegang tot in quarantaine geplaatste berichten voor alle gebruikers, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="67d23-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="67d23-124">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="67d23-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="67d23-125">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="67d23-125">**Notes**:</span></span>

  - <span data-ttu-id="67d23-126">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67d23-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="67d23-127">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="67d23-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="67d23-128">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="67d23-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="67d23-129"><sup>\*</sup> Leden van de rollengroep **Quarantainebeheerder** moeten ook lid zijn van de rollengroep **Hygiënebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) om quarantaineprocedures uit te voeren in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67d23-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="67d23-130">Berichten in quarantaine worden bewaard voor een standaardperiode voordat ze automatisch worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="67d23-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="67d23-131">30 dagen voor berichten die in quarantaine zijn geplaatst door antispambeleid (spam, phishing en bulk-e-mail).</span><span class="sxs-lookup"><span data-stu-id="67d23-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="67d23-132">Dit is de standaardwaarde en de maximumwaarde.</span><span class="sxs-lookup"><span data-stu-id="67d23-132">This is the default and maximum value.</span></span> <span data-ttu-id="67d23-133">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren (lager).</span><span class="sxs-lookup"><span data-stu-id="67d23-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="67d23-134">15 dagen voor berichten die malware bevatten.</span><span class="sxs-lookup"><span data-stu-id="67d23-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="67d23-135">15 dagen voor bestanden die in quarantaine zijn geplaatst door veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="67d23-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="67d23-136">Wanneer een bericht verloopt vanuit quarantaine, kunt u het bericht niet herstellen.</span><span class="sxs-lookup"><span data-stu-id="67d23-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="67d23-137">Het beveiligings- & compliancecentrum gebruiken om in quarantaine geplaatste e-mailberichten te beheren</span><span class="sxs-lookup"><span data-stu-id="67d23-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="67d23-138">In quarantaine geplaatste e-mail weergeven</span><span class="sxs-lookup"><span data-stu-id="67d23-138">View quarantined email</span></span>

1. <span data-ttu-id="67d23-139">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="67d23-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="67d23-140">Controleer of **Weergave in quarantaine** is ingesteld op de standaardwaarde-e-mail. </span><span class="sxs-lookup"><span data-stu-id="67d23-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="67d23-141">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="67d23-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="67d23-142">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="67d23-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="67d23-143">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="67d23-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="67d23-144">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-145">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-146">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-147">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-148">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-149">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-150">**Vervalt op**</span><span class="sxs-lookup"><span data-stu-id="67d23-150">**Expires**</span></span>
   - <span data-ttu-id="67d23-151">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="67d23-151">**Recipient**</span></span>
   - <span data-ttu-id="67d23-152">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="67d23-152">**Message ID**</span></span>
   - <span data-ttu-id="67d23-153">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="67d23-153">**Policy name**</span></span>
   - <span data-ttu-id="67d23-154">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="67d23-154">**Size**</span></span>
   - <span data-ttu-id="67d23-155">**Richting**</span><span class="sxs-lookup"><span data-stu-id="67d23-155">**Direction**</span></span>

   <span data-ttu-id="67d23-156">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="67d23-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="67d23-157">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="67d23-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="67d23-158">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="67d23-158">The available filters are:</span></span>

   - <span data-ttu-id="67d23-159">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="67d23-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="67d23-160">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="67d23-160">**Today**</span></span>
     - <span data-ttu-id="67d23-161">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="67d23-161">**Next 2 days**</span></span>
     - <span data-ttu-id="67d23-162">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="67d23-162">**Next 7 days**</span></span>
     - <span data-ttu-id="67d23-163">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="67d23-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="67d23-164">**Ontvangen op**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="67d23-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="67d23-165">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="67d23-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="67d23-166">**Beleid:** Het bericht komt overeen met de voorwaarden van een e-mailstroomregel (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="67d23-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="67d23-167">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="67d23-167">**Bulk**</span></span>
     - <span data-ttu-id="67d23-168">**Phish:** De uitspraak van het spamfilter was Phishing-e-mail of anti-phishingbeveiliging die het bericht in quarantaine heeft geplaatst [(spoofinstellingen](set-up-anti-phishing-policies.md#spoof-settings) of [imitatiebeveiliging).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) </span><span class="sxs-lookup"><span data-stu-id="67d23-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="67d23-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="67d23-169">**Malware**</span></span>
     - <span data-ttu-id="67d23-170">**Spam**</span><span class="sxs-lookup"><span data-stu-id="67d23-170">**Spam**</span></span>
     - <span data-ttu-id="67d23-171">**Phish met hoog vertrouwen**</span><span class="sxs-lookup"><span data-stu-id="67d23-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="67d23-172">**Beleidstype**: berichten filteren op beleidstype:</span><span class="sxs-lookup"><span data-stu-id="67d23-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="67d23-173">**Anti-malwarebeleid**</span><span class="sxs-lookup"><span data-stu-id="67d23-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="67d23-174">**Beleid voor veilige bijlagen**</span><span class="sxs-lookup"><span data-stu-id="67d23-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="67d23-175">**Beleid tegen phishing**</span><span class="sxs-lookup"><span data-stu-id="67d23-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="67d23-176">**Beleid voor gehoste inhoudsfilters** (antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="67d23-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="67d23-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="67d23-177">**Transport rule**</span></span>

   - <span data-ttu-id="67d23-178">**E-mailontvanger:** Alle gebruikers of alleen berichten die naar u zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="67d23-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="67d23-179">Eindgebruikers kunnen alleen in quarantaine geplaatste berichten beheren die naar hen zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="67d23-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="67d23-180">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="67d23-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="67d23-181">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="67d23-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="67d23-182">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="67d23-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="67d23-183">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="67d23-183">Wildcards aren't supported.</span></span> <span data-ttu-id="67d23-184">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="67d23-184">You can search by the following values:</span></span>

   - <span data-ttu-id="67d23-185">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="67d23-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="67d23-186">U hebt bijvoorbeeld [](message-trace-scc.md) berichtspoor gebruikt om te zoeken naar een bericht dat is verzonden naar een gebruiker in uw organisatie en u bepaalt dat het bericht in quarantaine is geplaatst in plaats van bezorgd.</span><span class="sxs-lookup"><span data-stu-id="67d23-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="67d23-187">Zorg ervoor dat u de id-waarde voor het volledige bericht op moet nemen, waaronder hoekhaken ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="67d23-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="67d23-188">Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="67d23-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="67d23-189">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="67d23-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="67d23-190">**Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht.</span><span class="sxs-lookup"><span data-stu-id="67d23-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="67d23-191">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="67d23-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="67d23-192">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="67d23-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="67d23-193">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="67d23-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="67d23-194">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="67d23-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="67d23-195">**Naam van** het beleid: de naam van het beleid dat verantwoordelijk was voor het kwaalveren van het bericht.</span><span class="sxs-lookup"><span data-stu-id="67d23-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="67d23-196">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="67d23-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="67d23-197">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="67d23-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="67d23-198">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="67d23-198">View quarantined message details</span></span>

<span data-ttu-id="67d23-199">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="67d23-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="67d23-200">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="67d23-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="67d23-201">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="67d23-201">**Sender address**</span></span>

- <span data-ttu-id="67d23-202">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="67d23-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="67d23-203">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="67d23-203">**Subject**</span></span>

- <span data-ttu-id="67d23-204">**Reden voor quarantaine:** geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish**, overeenkomend met een regel voor de e-mailstroom (**transportregel**) of is geïdentificeerd als **malware.**</span><span class="sxs-lookup"><span data-stu-id="67d23-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="67d23-205">**Aantal geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="67d23-205">**Recipient count**</span></span>

- <span data-ttu-id="67d23-206">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="67d23-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="67d23-207">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="67d23-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="67d23-208">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="67d23-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="67d23-209">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="67d23-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="67d23-210">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="67d23-210">Take action on quarantined email</span></span>

<span data-ttu-id="67d23-211">Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u moet doen met de berichten in het deelvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="67d23-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="67d23-212">**Releasebericht:** Kies de volgende opties in het flyoutvenster dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="67d23-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="67d23-213">**Berichten rapporteren aan Microsoft voor analyse:** Dit is standaard geselecteerd en meldt het verkeerd in quarantaine geplaatste bericht aan Microsoft als een onwaar positief bericht.</span><span class="sxs-lookup"><span data-stu-id="67d23-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="67d23-214">Als het bericht in quarantaine is geplaatst als spam, bulksgewijs, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="67d23-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="67d23-215">Afhankelijk van hun analyse kunnen de regels voor spamfilters voor de hele service worden aangepast om het bericht door te sturen.</span><span class="sxs-lookup"><span data-stu-id="67d23-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="67d23-216">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="67d23-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="67d23-217">**Berichten vrijgeven voor alle geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="67d23-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="67d23-218">**Berichten vrijgeven aan specifieke geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="67d23-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="67d23-219">**Berichten vrijgeven aan andere personen:** houd er rekening mee dat het vrijgeven van malwareberichten aan andere personen dan oorspronkelijke geadresseerden niet wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="67d23-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="67d23-220">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="67d23-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="67d23-221">Notities over het vrijgeven van berichten:</span><span class="sxs-lookup"><span data-stu-id="67d23-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="67d23-222">U kunt een bericht niet meer dan één keer vrijgeven aan dezelfde geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="67d23-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="67d23-223">Alleen geadresseerden die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="67d23-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="67d23-224">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="67d23-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="67d23-225">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="67d23-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="67d23-226">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="67d23-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="67d23-227">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="67d23-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="67d23-228">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="67d23-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="67d23-229">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="67d23-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="67d23-230">**Uit quarantaine verwijderen:** nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="67d23-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="67d23-231">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="67d23-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="67d23-232">**Afzender blokkeren:** Voeg de afzender toe aan de lijst Geblokkeerde afzenders in uw postvak.</span><span class="sxs-lookup"><span data-stu-id="67d23-232">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="67d23-233">Zie Een afzender van [e-mail blokkeren voor meer informatie.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="67d23-233">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="67d23-234">**Bericht verzenden:** Kies de volgende opties in het flyoutvenster dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="67d23-234">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="67d23-235">**Objecttype:** **E-mail** (standaard), **URL** of **Bijlage**.</span><span class="sxs-lookup"><span data-stu-id="67d23-235">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="67d23-236">**Inzendingsindeling:** **Netwerkbericht-id** (standaard,  met de bijbehorende waarde in het vak Netwerkbericht-id) **of** Bestand (bladeren naar een lokaal .eml- of .msg-bestand).</span><span class="sxs-lookup"><span data-stu-id="67d23-236">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="67d23-237">Als u Bestand **selecteert** en vervolgens **Netwerkbericht-id** selecteert, is de oorspronkelijke waarde verdwenen.</span><span class="sxs-lookup"><span data-stu-id="67d23-237">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="67d23-238">**Geadresseerden:** Typ bij lease één oorspronkelijke geadresseerde van het bericht of klik **op Alles selecteren** om alle geadresseerden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="67d23-238">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="67d23-239">U kunt ook op **Alles selecteren** klikken en afzonderlijke geadresseerden vervolgens selectief verwijderen.</span><span class="sxs-lookup"><span data-stu-id="67d23-239">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="67d23-240">**Reden voor indiening:** **Had niet moeten worden geblokkeerd** (standaard) of Had moeten worden **geblokkeerd.**</span><span class="sxs-lookup"><span data-stu-id="67d23-240">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="67d23-241">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="67d23-241">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="67d23-242">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="67d23-242">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="67d23-243">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="67d23-243">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="67d23-244">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="67d23-244">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="67d23-245">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="67d23-245">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="67d23-246">Houd rekening met het volgende scenario: john@gmail.com stuurt een bericht naar faith@contoso.com en john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="67d23-246">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="67d23-247">Gmail zet dit bericht op in twee exemplaren die beide naar quarantaine worden gerouteerd als phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67d23-247">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="67d23-248">Een beheerder geeft beide berichten vrij aan admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="67d23-248">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="67d23-249">Het eerste uitgebrachte bericht dat het postvak van de beheerder bereikt, wordt bezorgd.</span><span class="sxs-lookup"><span data-stu-id="67d23-249">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="67d23-250">Het tweede uitgebrachte bericht wordt geïdentificeerd als dubbele bezorging en wordt overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="67d23-250">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="67d23-251">Berichten worden geïdentificeerd als duplicaten als ze dezelfde bericht-id en ontvangen tijd hebben.</span><span class="sxs-lookup"><span data-stu-id="67d23-251">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="67d23-252">**Berichten verwijderen:** Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="67d23-252">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="67d23-253">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="67d23-253">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="67d23-254">Alleen Microsoft Defender voor Office 365: Gebruik het beveiligings- & compliancecentrum om in quarantaine geplaatste bestanden te beheren</span><span class="sxs-lookup"><span data-stu-id="67d23-254">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="67d23-255">De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor abonnees van Microsoft Defender voor Office 365 Abonnement 1 en Abonnement 2.</span><span class="sxs-lookup"><span data-stu-id="67d23-255">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="67d23-256">In organisaties met Defender voor Office 365 kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67d23-256">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="67d23-257">Zie Veilige bijlagen inschakelen voor [SharePoint, OneDrive en Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)als u de beveiliging van deze bestanden wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="67d23-257">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="67d23-258">In quarantaine geplaatste bestanden weergeven</span><span class="sxs-lookup"><span data-stu-id="67d23-258">View quarantined files</span></span>

1. <span data-ttu-id="67d23-259">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="67d23-259">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="67d23-260">Weergave **in quarantaine wijzigen in** de **waardebestanden.**</span><span class="sxs-lookup"><span data-stu-id="67d23-260">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="67d23-261">U kunt sorteren op een veld door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="67d23-261">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="67d23-262">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="67d23-262">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="67d23-263">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="67d23-263">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="67d23-264">De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="67d23-264">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="67d23-265">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-265">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-266">**Locatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-266">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-267">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-267">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-268">**BestandS-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-268">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-269">**Bestandsgrootte**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-269">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-270">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-270">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-271">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="67d23-271">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="67d23-272">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="67d23-272">**Detected by**</span></span>
   - <span data-ttu-id="67d23-273">**Gewijzigd op tijd**</span><span class="sxs-lookup"><span data-stu-id="67d23-273">**Modified by time**</span></span>

4. <span data-ttu-id="67d23-274">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="67d23-274">To filter the results, click **Filter**.</span></span> <span data-ttu-id="67d23-275">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="67d23-275">The available filters are:</span></span>

   - <span data-ttu-id="67d23-276">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="67d23-276">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="67d23-277">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="67d23-277">**Today**</span></span>
     - <span data-ttu-id="67d23-278">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="67d23-278">**Next 2 days**</span></span>
     - <span data-ttu-id="67d23-279">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="67d23-279">**Next 7 days**</span></span>
     - <span data-ttu-id="67d23-280">Een aangepast datum-/tijdbereik.</span><span class="sxs-lookup"><span data-stu-id="67d23-280">A custom date/time range.</span></span>
   - <span data-ttu-id="67d23-281">**Ontvangen tijd**</span><span class="sxs-lookup"><span data-stu-id="67d23-281">**Received time**</span></span>
   - <span data-ttu-id="67d23-282">**Reden voor quarantaine:** De enige beschikbare waarde is **Malware.**</span><span class="sxs-lookup"><span data-stu-id="67d23-282">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="67d23-283">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="67d23-283">**Policy type**</span></span>

<span data-ttu-id="67d23-284">Nadat u een specifiek bestand in quarantaine hebt gevonden, selecteert u het bestand om de details ervan weer te geven en om actie te ondernemen (bijvoorbeeld het bericht weergeven, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="67d23-284">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="67d23-285">In quarantaine geplaatste bestandsgegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="67d23-285">View quarantined file details</span></span>

<span data-ttu-id="67d23-286">Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsgegevens weergegeven in het deelvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="67d23-286">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="67d23-287">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="67d23-287">**File Name**</span></span>
- <span data-ttu-id="67d23-288">**BestandS-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="67d23-288">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="67d23-289">**Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="67d23-289">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="67d23-290">**Verloopt:** De datum waarop het bestand uit quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="67d23-290">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="67d23-291">**Gedetecteerd door**: Defender voor Office 365 of de anti-malware-engine van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67d23-291">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="67d23-292">**Vrijgegeven?**</span><span class="sxs-lookup"><span data-stu-id="67d23-292">**Released?**</span></span>
- <span data-ttu-id="67d23-293">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="67d23-293">**Malware Name**</span></span>
- <span data-ttu-id="67d23-294">**Document-id:** een unieke id voor het document.</span><span class="sxs-lookup"><span data-stu-id="67d23-294">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="67d23-295">**Bestandsgrootte:** in kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="67d23-295">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="67d23-296">**Organisatie** De unieke id van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="67d23-296">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="67d23-297">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="67d23-297">**Last modified**</span></span>
- <span data-ttu-id="67d23-298">**Gewijzigd door**: De gebruiker die het bestand het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="67d23-298">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="67d23-299">**Secure Hash Algorithm 256-bits (SHA-256)** waarde: U kunt deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiestores of op andere locaties in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="67d23-299">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="67d23-300">Actie ondernemen voor in quarantaine geplaatste bestanden</span><span class="sxs-lookup"><span data-stu-id="67d23-300">Take action on quarantined files</span></span>

<span data-ttu-id="67d23-301">Wanneer u een bestand in de lijst selecteert, kunt u de volgende acties uitvoeren in het bestand in het deelvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="67d23-301">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="67d23-302">**Releasebestanden:** Selecteer (standaard) of deselecteer **Rapportbestanden** naar Microsoft voor analyse en klik vervolgens op **Bestanden vrijgeven.**</span><span class="sxs-lookup"><span data-stu-id="67d23-302">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="67d23-303">**Downloadbestand**</span><span class="sxs-lookup"><span data-stu-id="67d23-303">**Download file**</span></span>
- <span data-ttu-id="67d23-304">**Bestand uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="67d23-304">**Remove file from quarantine**</span></span>

<span data-ttu-id="67d23-305">Als u de bestanden niet los laat of verwijdert, worden deze verwijderd nadat de standaard bewaarperiode voor quarantaine is verlopen.</span><span class="sxs-lookup"><span data-stu-id="67d23-305">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="67d23-306">Acties voor meerdere in quarantaine geplaatste bestanden</span><span class="sxs-lookup"><span data-stu-id="67d23-306">Actions on multiple quarantined files</span></span>

<span data-ttu-id="67d23-307">Wanneer u meerdere in quarantaine geplaatste bestanden in de  lijst selecteert (maximaal 100), wordt het deelvenster Bulkacties weergegeven waarin u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="67d23-307">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="67d23-308">**Bestanden vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="67d23-308">**Release files**</span></span>
- <span data-ttu-id="67d23-309">**Bestanden verwijderen:** Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de bestanden onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="67d23-309">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="67d23-310">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om in quarantaine geplaatste berichten en bestanden weer te geven en te beheren</span><span class="sxs-lookup"><span data-stu-id="67d23-310">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="67d23-311">De cmdlets die u gebruikt voor het weergeven en beheren van berichten en bestanden in quarantaine zijn:</span><span class="sxs-lookup"><span data-stu-id="67d23-311">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="67d23-312">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67d23-312">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="67d23-313">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67d23-313">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="67d23-314">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67d23-314">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="67d23-315">[Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)Deze cmdlet is alleen voor berichten, niet voor bestanden in quarantaine geplaatst vanuit veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67d23-315">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="67d23-316">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="67d23-316">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
