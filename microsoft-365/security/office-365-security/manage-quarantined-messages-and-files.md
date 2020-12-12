---
title: Berichten en bestanden in quarantaine beheren als beheerder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
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
description: Beheerders kunnen informatie lezen over het weergeven en beheren van quarantaine berichten voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook quarantaine bestanden beheren in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659984"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="0b0df-104">Berichten en bestanden in quarantaine beheren als EOP-beheerder</span><span class="sxs-lookup"><span data-stu-id="0b0df-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0b0df-105">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="0b0df-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="0b0df-106">Zie voor meer informatie [Gequarantinee e-mailberichten in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0b0df-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="0b0df-107">Beheerders kunnen alle typen quarantaine berichten voor alle gebruikers weergeven, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="0b0df-108">Alleen beheerders kunnen berichten beheren die zijn gequarantined met malware, phishing van hoge betrouwbaarheid of als gevolg van de regels voor de e-mail stroom (ook wel transport regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="0b0df-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="0b0df-109">Beheerders kunnen ook fout-positieven rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b0df-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="0b0df-110">Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams weergeven, downloaden en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="0b0df-111">U kunt berichten in quarantaine weergeven en beheren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="0b0df-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b0df-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0b0df-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b0df-113">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="0b0df-114">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="0b0df-115">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b0df-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0b0df-116">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b0df-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b0df-117">Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="0b0df-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0b0df-118">Als u een actie wilt uitvoeren op berichten in quarantaine voor alle gebruikers, moet u lid zijn van de rollen groepen **Organisatiebeheer**, **beveiliging beheerder** of **quarantaine beheerder** <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="0b0df-118">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="0b0df-119">Voor alleen-lezen toegang tot quarantaine berichten voor alle gebruikers moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="0b0df-119">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0b0df-120">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b0df-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="0b0df-121">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="0b0df-121">**Notes**:</span></span>

  - <span data-ttu-id="0b0df-122">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b0df-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0b0df-123">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b0df-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="0b0df-124">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="0b0df-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="0b0df-125"><sup>\*</sup> Leden van de rollen groep **Quarantine beheerder** moeten ook lid zijn van de rollen groep **hygiëne beheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) om quarantaine procedures uit te voeren in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b0df-125"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="0b0df-126">Berichten in quarantaine worden gedurende een standaardperiode bewaard voordat ze automatisch worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="0b0df-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="0b0df-127">30 dagen voor berichten die zijn gequarantined door Antispambeleid (spam, phishing en bulk-e-mail).</span><span class="sxs-lookup"><span data-stu-id="0b0df-127">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="0b0df-128">Dit is de standaard-en maximumwaarde.</span><span class="sxs-lookup"><span data-stu-id="0b0df-128">This is the default and maximum value.</span></span> <span data-ttu-id="0b0df-129">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)voor het configureren van deze waarde.</span><span class="sxs-lookup"><span data-stu-id="0b0df-129">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="0b0df-130">15 dagen voor berichten die malware bevatten.</span><span class="sxs-lookup"><span data-stu-id="0b0df-130">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="0b0df-131">15 dagen voor bestanden die worden Quarantine door ATP voor SharePoint, OneDrive en Microsoft teams in de Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="0b0df-131">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="0b0df-132">Wanneer een bericht verloopt over quarantaine, kunt u dit niet herstellen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-132">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="0b0df-133">De beveiligings & voor compliance gebruiken voor het beheren van e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0b0df-133">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="0b0df-134">Gequarantinede e-mail weergeven</span><span class="sxs-lookup"><span data-stu-id="0b0df-134">View quarantined email</span></span>

1. <span data-ttu-id="0b0df-135">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-135">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="0b0df-136">Controleer of **weergave in quarantaine** is ingesteld op de standaardwaarde **-e-mail**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-136">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="0b0df-137">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="0b0df-137">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="0b0df-138">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="0b0df-138">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="0b0df-139">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="0b0df-139">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="0b0df-140">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-140">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-141">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-141">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-142">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-142">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-143">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-143">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-144">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-144">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-145">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-145">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-146">**Vervalt op**</span><span class="sxs-lookup"><span data-stu-id="0b0df-146">**Expires**</span></span>
   - <span data-ttu-id="0b0df-147">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="0b0df-147">**Recipient**</span></span>
   - <span data-ttu-id="0b0df-148">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="0b0df-148">**Message ID**</span></span>
   - <span data-ttu-id="0b0df-149">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="0b0df-149">**Policy name**</span></span>
   - <span data-ttu-id="0b0df-150">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="0b0df-150">**Size**</span></span>
   - <span data-ttu-id="0b0df-151">**Richting**</span><span class="sxs-lookup"><span data-stu-id="0b0df-151">**Direction**</span></span>

   <span data-ttu-id="0b0df-152">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0b0df-152">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="0b0df-153">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="0b0df-153">To filter the results, click **Filter**.</span></span> <span data-ttu-id="0b0df-154">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="0b0df-154">The available filters are:</span></span>

   - <span data-ttu-id="0b0df-155">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="0b0df-155">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="0b0df-156">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="0b0df-156">**Today**</span></span>
     - <span data-ttu-id="0b0df-157">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="0b0df-157">**Next 2 days**</span></span>
     - <span data-ttu-id="0b0df-158">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="0b0df-158">**Next 7 days**</span></span>
     - <span data-ttu-id="0b0df-159">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="0b0df-159">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="0b0df-160">**Ontvangen op**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="0b0df-160">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="0b0df-161">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="0b0df-161">**Quarantine reason**:</span></span>
     - <span data-ttu-id="0b0df-162">**Beleid**: het bericht voldoet aan de voorwaarden van een e-mail stroom regel (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="0b0df-162">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="0b0df-163">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="0b0df-163">**Bulk**</span></span>
     - <span data-ttu-id="0b0df-164">**Phishing**: de spamfilter verdict was **phishing-e-mail** of Anti Phishing Protection het bericht ([spoof-instellingen](set-up-anti-phishing-policies.md#spoof-settings) of [imitatie bescherming](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="0b0df-164">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="0b0df-165">**Malware**</span><span class="sxs-lookup"><span data-stu-id="0b0df-165">**Malware**</span></span>
     - <span data-ttu-id="0b0df-166">**Spam**</span><span class="sxs-lookup"><span data-stu-id="0b0df-166">**Spam**</span></span>
     - <span data-ttu-id="0b0df-167">**Hoge betrouwbaarheid van phishing**</span><span class="sxs-lookup"><span data-stu-id="0b0df-167">**High Confidence Phish**</span></span>

   - <span data-ttu-id="0b0df-168">**Beleidstype**: berichten filteren op beleidstype:</span><span class="sxs-lookup"><span data-stu-id="0b0df-168">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="0b0df-169">**Anti malwarebeleid**</span><span class="sxs-lookup"><span data-stu-id="0b0df-169">**Anti-malware policy**</span></span>
     - <span data-ttu-id="0b0df-170">**Beleid voor veilige bijlagen**</span><span class="sxs-lookup"><span data-stu-id="0b0df-170">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="0b0df-171">**Beleid tegen phishing**</span><span class="sxs-lookup"><span data-stu-id="0b0df-171">**Anti-phish policy**</span></span>
     - <span data-ttu-id="0b0df-172">**Beleid voor gehoste inhoudsfilters** (antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="0b0df-172">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="0b0df-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="0b0df-173">**Transport rule**</span></span>

   - <span data-ttu-id="0b0df-174">**E-mail ontvanger**: alle gebruikers of alleen berichten die naar u zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="0b0df-174">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="0b0df-175">Eindgebruikers kunnen alleen quarantaine berichten beheren die ze hebben verzonden.</span><span class="sxs-lookup"><span data-stu-id="0b0df-175">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="0b0df-176">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="0b0df-177">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-177">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="0b0df-178">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="0b0df-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="0b0df-179">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="0b0df-179">Wildcards aren't supported.</span></span> <span data-ttu-id="0b0df-180">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="0b0df-180">You can search by the following values:</span></span>

   - <span data-ttu-id="0b0df-181">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0b0df-181">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="0b0df-182">U gebruikt bijvoorbeeld de [bericht tracering](message-trace-scc.md) om te zoeken naar een bericht dat is verzonden naar een gebruiker in uw organisatie en u hebt vastgesteld dat het bericht is in quarantaine geplaatst in plaats van afgeleverd.</span><span class="sxs-lookup"><span data-stu-id="0b0df-182">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="0b0df-183">Zorg ervoor dat u de volledige waarde voor de bericht-ID opneemt, waaronder punthaken ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="0b0df-183">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="0b0df-184">Voor `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` Beeld:</span><span class="sxs-lookup"><span data-stu-id="0b0df-184">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="0b0df-185">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="0b0df-185">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="0b0df-186">**Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0b0df-186">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="0b0df-187">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="0b0df-187">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="0b0df-188">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="0b0df-188">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="0b0df-189">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0b0df-189">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="0b0df-190">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="0b0df-190">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="0b0df-191">**Beleidsnaam**: de naam van het beleid dat verantwoordelijk is voor het quarantining van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0b0df-191">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="0b0df-192">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="0b0df-192">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="0b0df-193">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="0b0df-193">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="0b0df-194">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="0b0df-194">View quarantined message details</span></span>

<span data-ttu-id="0b0df-195">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="0b0df-195">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0b0df-196">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0b0df-196">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="0b0df-197">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="0b0df-197">**Sender address**</span></span>

- <span data-ttu-id="0b0df-198">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-198">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="0b0df-199">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="0b0df-199">**Subject**</span></span>

- <span data-ttu-id="0b0df-200">**Reden voor quarantaine**: geeft aan of een bericht als **spam**, **bulksgewijs**, **phishing** of in overeenstemming met een e-mail stroom regel (**transport regel**) is geïdentificeerd, of dat is geïdentificeerd als **malware**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-200">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="0b0df-201">**Aantal geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="0b0df-201">**Recipient count**</span></span>

- <span data-ttu-id="0b0df-202">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="0b0df-202">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="0b0df-203">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="0b0df-203">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="0b0df-204">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="0b0df-204">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="0b0df-205">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="0b0df-205">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="0b0df-206">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0b0df-206">Take action on quarantined email</span></span>

<span data-ttu-id="0b0df-207">Wanneer u een bericht hebt geselecteerd, kunt u in het vervolgmenu **Details** verschillende opties opgeven voor wat u wilt doen met de berichten:</span><span class="sxs-lookup"><span data-stu-id="0b0df-207">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0b0df-208">**Release bericht**: Kies in het deelvenster flyout dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="0b0df-208">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="0b0df-209">**Meld u aan bij Microsoft for Analysis**: deze optie is standaard geselecteerd en rapporten geeft het abusievelijk gequarantinee bericht aan Microsoft als een onwaar positief.</span><span class="sxs-lookup"><span data-stu-id="0b0df-209">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="0b0df-210">Als het bericht is gequarantined als spam, bulksgewijs, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft spam Analysis-Team.</span><span class="sxs-lookup"><span data-stu-id="0b0df-210">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="0b0df-211">Afhankelijk van de analyse kunnen de regels voor spamfilters van het serviceniveau worden aangepast om het bericht toe te staan.</span><span class="sxs-lookup"><span data-stu-id="0b0df-211">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="0b0df-212">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="0b0df-212">Choose one of the following options:</span></span>
    - <span data-ttu-id="0b0df-213">**Berichten uitbrengen voor alle geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="0b0df-213">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="0b0df-214">**Berichten vrijgeven aan specifieke geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="0b0df-214">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="0b0df-215">**Berichten uitbrengen voor andere personen**: Opmerking: het vrijgeven van malware-berichten aan andere personen dan originele geadresseerden wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="0b0df-215">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="0b0df-216">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0b0df-216">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="0b0df-217">Opmerkingen over het vrijgeven van berichten:</span><span class="sxs-lookup"><span data-stu-id="0b0df-217">Notes about releasing messages:</span></span>

  - <span data-ttu-id="0b0df-218">U kunt een bericht niet meer dan één keer vrijgeven voor dezelfde geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="0b0df-218">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="0b0df-219">Alleen geadresseerden die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="0b0df-219">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="0b0df-220">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0b0df-220">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="0b0df-221">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="0b0df-221">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="0b0df-222">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="0b0df-222">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="0b0df-223">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="0b0df-223">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="0b0df-224">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-224">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="0b0df-225">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="0b0df-225">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="0b0df-226">**Uit quarantaine verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht direct verwijderd zonder dat het naar de oorspronkelijke geadresseerden wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="0b0df-226">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="0b0df-227">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="0b0df-227">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="0b0df-228">**Bericht verzenden**: Kies de volgende opties in het deelvenster flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="0b0df-228">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="0b0df-229">**Object type**: **e-mail** (standaard), **URL** of **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-229">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="0b0df-230">**Indeling voor indienen**: **netwerkbericht-id** (standaard met de overeenkomstige waarde in het vak **netwerkbericht-id** ) of **bestand** (Blader naar een Local. eml-of. msg-bestand).</span><span class="sxs-lookup"><span data-stu-id="0b0df-230">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="0b0df-231">Houd er rekening mee dat als u **bestand** selecteert en vervolgens **netwerkbericht-id** selecteert, de aanvankelijke waarde is verdwenen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-231">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="0b0df-232">**Geadresseerden**: Typ een originele geadresseerde van het bericht, of klik op **Alles selecteren** om alle geadresseerden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="0b0df-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="0b0df-233">U kunt ook op **de knop Alles selecteren** klikken en vervolgens selectief afzonderlijke geadresseerden verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-233">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="0b0df-234">**Reden voor indiening**: **mag niet zijn geblokkeerd** (standaardinstelling) of **moet zijn geblokkeerd**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-234">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="0b0df-235">Als u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-235">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="0b0df-236">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-236">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="0b0df-237">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0b0df-237">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="0b0df-238">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0b0df-238">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="0b0df-239">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-239">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0b0df-240">Kijk eens naar het volgende scenario: john@gmail.com verzendt een bericht naar faith@contoso.com en john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0b0df-240">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="0b0df-241">Gmail bifurcates dit bericht in twee kopieën die beide worden gerouteerd naar Quarantine als phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b0df-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="0b0df-242">Een beheerder geeft beide berichten vrij op admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0b0df-242">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="0b0df-243">Het eerste uitgebrachte bericht waarin het postvak van de beheerder is bereikt, wordt bezorgd.</span><span class="sxs-lookup"><span data-stu-id="0b0df-243">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="0b0df-244">Het tweede uitgebrachte bericht wordt geïdentificeerd als duplicaten ontvangst en wordt overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-244">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="0b0df-245">Berichten worden geïdentificeerd als duplicaten als ze dezelfde bericht-ID hebben en tijd hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-245">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="0b0df-246">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd zonder dat ze naar de oorspronkelijke geadresseerden worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="0b0df-246">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="0b0df-247">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0b0df-247">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="0b0df-248">Microsoft Defender voor Office 365: alleen met behulp van het compliance-& Beveiligingscentrum voor het beheren van bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0b0df-248">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="0b0df-249">De procedures voor de in deze sectie beschikbare bestanden zijn alleen beschikbaar voor Microsoft Defender voor Office 365, abonnement 1 en abonnementen op abonnement 2.</span><span class="sxs-lookup"><span data-stu-id="0b0df-249">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="0b0df-250">In organisaties met Defender voor Office 365 kunnen beheerders quarantaine bestanden beheren in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0b0df-250">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="0b0df-251">Zie [ATP voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md)inschakelen om beveiliging voor deze bestanden in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-251">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="0b0df-252">Bestanden met quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="0b0df-252">View quarantined files</span></span>

1. <span data-ttu-id="0b0df-253">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-253">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="0b0df-254">Wijzig de **weergave in quarantaine** voor de Value **files**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-254">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="0b0df-255">U kunt op een veld sorteren door te klikken op een beschikbare kolomkop.</span><span class="sxs-lookup"><span data-stu-id="0b0df-255">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="0b0df-256">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="0b0df-256">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="0b0df-257">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="0b0df-257">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="0b0df-258">De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="0b0df-258">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="0b0df-259">**Aanmeldings**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-259">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-260">**Locatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-260">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-261">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-261">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-262">**Bestands-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-262">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-263">**Bestandsgrootte**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-263">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-264">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-264">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-265">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0b0df-265">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="0b0df-266">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="0b0df-266">**Detected by**</span></span>
   - <span data-ttu-id="0b0df-267">**Gewijzigd door de tijd**</span><span class="sxs-lookup"><span data-stu-id="0b0df-267">**Modified by time**</span></span>

4. <span data-ttu-id="0b0df-268">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="0b0df-268">To filter the results, click **Filter**.</span></span> <span data-ttu-id="0b0df-269">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="0b0df-269">The available filters are:</span></span>

   - <span data-ttu-id="0b0df-270">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="0b0df-270">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="0b0df-271">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="0b0df-271">**Today**</span></span>
     - <span data-ttu-id="0b0df-272">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="0b0df-272">**Next 2 days**</span></span>
     - <span data-ttu-id="0b0df-273">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="0b0df-273">**Next 7 days**</span></span>
     - <span data-ttu-id="0b0df-274">Een aangepast datum/tijdbereik.</span><span class="sxs-lookup"><span data-stu-id="0b0df-274">A custom date/time range.</span></span>
   - <span data-ttu-id="0b0df-275">**Tijdstip van de ontvangst**</span><span class="sxs-lookup"><span data-stu-id="0b0df-275">**Received time**</span></span>
   - <span data-ttu-id="0b0df-276">**Reden voor quarantaine**: de enige beschikbare waarde is **malware**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-276">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="0b0df-277">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="0b0df-277">**Policy type**</span></span>

<span data-ttu-id="0b0df-278">Wanneer u een specifiek in quarantaine geplaatste bestand hebt gevonden, selecteert u het bestand om de details ervan weer te geven, en kunt u actie ondernemen (u kunt het bericht bijvoorbeeld weergeven, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="0b0df-278">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="0b0df-279">Details van bestand met quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="0b0df-279">View quarantined file details</span></span>

<span data-ttu-id="0b0df-280">Wanneer u een bestand in de lijst selecteert, worden de volgende details van het bestand weergegeven in het deelvenster **Details** :</span><span class="sxs-lookup"><span data-stu-id="0b0df-280">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0b0df-281">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="0b0df-281">**File Name**</span></span>
- <span data-ttu-id="0b0df-282">**Bestands-URL**: URL waarmee de locatie van het bestand wordt gedefinieerd (bijvoorbeeld in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="0b0df-282">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="0b0df-283">**Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand is gequarantined.</span><span class="sxs-lookup"><span data-stu-id="0b0df-283">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="0b0df-284">**Verloopt** op: de datum waarop het bestand in quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0b0df-284">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="0b0df-285">**Gedetecteerd door**: Defender for Office 365 of de anti malware-engine van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b0df-285">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="0b0df-286">**Vrijgegeven?**</span><span class="sxs-lookup"><span data-stu-id="0b0df-286">**Released?**</span></span>
- <span data-ttu-id="0b0df-287">**Naam van malware**</span><span class="sxs-lookup"><span data-stu-id="0b0df-287">**Malware Name**</span></span>
- <span data-ttu-id="0b0df-288">**Document-id**: een unieke id voor het document.</span><span class="sxs-lookup"><span data-stu-id="0b0df-288">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="0b0df-289">**Bestandsgrootte**: in kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="0b0df-289">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="0b0df-290">**Organisatie** Unieke ID van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0b0df-290">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="0b0df-291">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="0b0df-291">**Last modified**</span></span>
- <span data-ttu-id="0b0df-292">**Gewijzigd door**: de gebruiker die het bestand het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="0b0df-292">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="0b0df-293">**Secure Hash Algorithm 256-bit (SHA-256)**: u kunt deze hash-waarde gebruiken om het bestand te identificeren in andere reputatie winkels of op andere locaties in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="0b0df-293">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="0b0df-294">Actie ondernemen op bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0b0df-294">Take action on quarantined files</span></span>

<span data-ttu-id="0b0df-295">Wanneer u een bestand in de lijst selecteert, kunt u de volgende acties voor het bestand in het deelvenster met **Details** van de vervolgkeuzelijst opnemen:</span><span class="sxs-lookup"><span data-stu-id="0b0df-295">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0b0df-296">**Release bestanden**: Selecteer (standaardinstelling) of hef de selectie **van de bestanden voor Microsoft** op en klik vervolgens op **bestanden vrijgeven**.</span><span class="sxs-lookup"><span data-stu-id="0b0df-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="0b0df-297">**Bestand downloaden**</span><span class="sxs-lookup"><span data-stu-id="0b0df-297">**Download file**</span></span>
- <span data-ttu-id="0b0df-298">**Het bestand verwijderen uit Quarantine**</span><span class="sxs-lookup"><span data-stu-id="0b0df-298">**Remove file from quarantine**</span></span>

<span data-ttu-id="0b0df-299">Als u de bestanden niet uitgeeft of verwijdert, worden deze verwijderd nadat de standaard bewaarperiode voor quarantaine is verlopen.</span><span class="sxs-lookup"><span data-stu-id="0b0df-299">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="0b0df-300">Acties op meerdere gequarantinee bestanden</span><span class="sxs-lookup"><span data-stu-id="0b0df-300">Actions on multiple quarantined files</span></span>

<span data-ttu-id="0b0df-301">Wanneer u in de lijst meerdere quarantaine bestanden selecteert (maximaal 100), wordt het menu met de opdracht **bulk acties** weergegeven, waarin u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0b0df-301">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="0b0df-302">**Bestanden vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="0b0df-302">**Release files**</span></span>
- <span data-ttu-id="0b0df-303">**Bestanden verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die verschijnt, worden de bestanden direct verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0b0df-303">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="0b0df-304">PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken om quarantaine berichten en-bestanden weer te geven en te beheren</span><span class="sxs-lookup"><span data-stu-id="0b0df-304">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="0b0df-305">De cmdlets die u gebruikt voor het weergeven en beheren van berichten en bestanden in quarantaine, zijn:</span><span class="sxs-lookup"><span data-stu-id="0b0df-305">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="0b0df-306">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="0b0df-306">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="0b0df-307">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="0b0df-307">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="0b0df-308">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="0b0df-308">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="0b0df-309">[Voorbeeld: QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): deze cmdlet is alleen voor berichten, geen malware-bestanden uit de ATP voor SharePoint Online, OneDrive voor bedrijven of teams.</span><span class="sxs-lookup"><span data-stu-id="0b0df-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="0b0df-310">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="0b0df-310">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
