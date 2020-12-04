---
title: Spoofberichten configureren
f1.keywords:
- NOCSH
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
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over spoof Intelligence in Exchange Online Protection (EOP), waar u specifieke afzenders kunt toestaan of blokkeren.
ms.openlocfilehash: 9168d43e6e5544ad3454729afc8140642deba0ef
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572727"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="2f707-103">Spoof informatie configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="2f707-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2f707-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvakken van Exchange Online worden inkomende e-mailberichten automatisch beveiligd tegen spoofing door EOP vanaf oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="2f707-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="2f707-105">EOP maakt gebruik van spoof Intelligence als onderdeel van de algemene verdediging van uw organisatie tegen phishing.</span><span class="sxs-lookup"><span data-stu-id="2f707-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="2f707-106">Zie [anti-spoofing beveiliging in EOP](anti-spoofing-protection.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="2f707-107">Wanneer een afzender een e-mailadres vervalst, lijken ze een gebruiker in een van de domeinen van uw organisatie of een gebruiker in een extern domein die e-mail naar uw organisatie verzendt.</span><span class="sxs-lookup"><span data-stu-id="2f707-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="2f707-108">Kwaadwillenden die afzenders vervalsen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="2f707-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="2f707-109">Er zijn echter scenario's waarbij originele afzenders spoofing zijn.</span><span class="sxs-lookup"><span data-stu-id="2f707-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="2f707-110">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2f707-110">For example:</span></span>

- <span data-ttu-id="2f707-111">Legitieme scenario's voor het spoofen van interne domeinen:</span><span class="sxs-lookup"><span data-stu-id="2f707-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="2f707-112">Afzenders van derden uw domein gebruiken om bulkmail te versturen naar uw eigen werknemers voor bedrijfs polls.</span><span class="sxs-lookup"><span data-stu-id="2f707-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="2f707-113">Een extern bedrijf genereert en stuurt namens u advertenties of productupdates.</span><span class="sxs-lookup"><span data-stu-id="2f707-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="2f707-114">Een assistent moet regelmatig e-mail verzenden voor een andere persoon binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="2f707-115">Een interne toepassing verzendt e-mail meldingen.</span><span class="sxs-lookup"><span data-stu-id="2f707-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="2f707-116">Legitieme scenario's voor het vervalsen van externe domeinen:</span><span class="sxs-lookup"><span data-stu-id="2f707-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="2f707-117">De afzender bevindt zich in een adressenlijst (ook wel discussielijst genoemd), en de adressenlijst stuurt e-mail van de oorspronkelijke afzender door naar alle deelnemers aan de adressenlijst.</span><span class="sxs-lookup"><span data-stu-id="2f707-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="2f707-118">Een extern bedrijf verzendt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-servicebedrijf).</span><span class="sxs-lookup"><span data-stu-id="2f707-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="2f707-119">Spoof Intelligence en specifiek het standaardbeleid voor spoof informatie van spoofing helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders is verzonden, niet wordt weergegeven in EOP spamfilters of externe e-mail systemen, terwijl u uw gebruikers tegen spam of phishing-aanvallen beschermt.</span><span class="sxs-lookup"><span data-stu-id="2f707-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="2f707-120">U kunt spoof Intelligence beheren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="2f707-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f707-121">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2f707-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f707-122">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2f707-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2f707-123">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="2f707-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="2f707-124">Als u rechtstreeks naar de **anti malafide** pagina wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="2f707-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="2f707-125">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f707-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2f707-126">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f707-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2f707-127">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor beveiliging & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="2f707-127">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2f707-128">Als u het beleid voor spoof informatie wilt wijzigen of spoof Intelligence wilt in-of uitschakelen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="2f707-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2f707-129">Voor alleen-lezen toegang tot het beleid voor spoof Intelligence moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="2f707-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2f707-130">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="2f707-131">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="2f707-131">**Notes**:</span></span>

  - <span data-ttu-id="2f707-132">Door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het Microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in het beveiligings & nalevings centrum _en_ machtigingen voor andere functies in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f707-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2f707-133">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-133">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="2f707-134">De functiegroep **alleen weergeven voor Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.</span><span class="sxs-lookup"><span data-stu-id="2f707-134">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="2f707-135">Voor de aanbevolen instellingen voor spoof Intelligence raadpleegt u [EOP standaard anti phishingfilter-beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="2f707-135">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="2f707-136">Het nalevings centrum voor beveiliging & gebruiken om vervalste afzenders te beheren</span><span class="sxs-lookup"><span data-stu-id="2f707-136">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="2f707-137">Als u een Microsoft 365 Enterprise E5-abonnement hebt of als u een invoegtoepassing voor Microsoft Defender voor Office 365 apart hebt aangeschaft, kunt u ook afzenders beheren die een spoofing van uw domein hebben via het [inzicht in spoof Intelligence](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-137">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="2f707-138">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="2f707-138">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="2f707-139">Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om het **spoof Intelligence-beleid** uit te vouwen.</span><span class="sxs-lookup"><span data-stu-id="2f707-139">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Het beleid voor spoof informatie selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="2f707-141">Voer een van de volgende opties in:</span><span class="sxs-lookup"><span data-stu-id="2f707-141">Make one of the following selections:</span></span>

   - <span data-ttu-id="2f707-142">**Nieuwe afzenders controleren**</span><span class="sxs-lookup"><span data-stu-id="2f707-142">**Review new senders**</span></span>
   - <span data-ttu-id="2f707-143">**Laat afzenders zien die ik al heb herzien**</span><span class="sxs-lookup"><span data-stu-id="2f707-143">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="2f707-144">Selecteer een van de volgende tabbladen in het menu **bepalen of deze afzenders toestemming hebben om uw gebruikers flyout te vervalsen** dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2f707-144">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="2f707-145">**Uw domeinen**: afzenders van afzenders gebruikers in uw interne domeinen.</span><span class="sxs-lookup"><span data-stu-id="2f707-145">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="2f707-146">**Externe domeinen**: afzenders spoofing gebruikers in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="2f707-146">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="2f707-147">Klik op ![ het pictogram uitvouwen ](../../media/scc-expand-icon.png) in de kolom **toegestaan voor spoof?** .</span><span class="sxs-lookup"><span data-stu-id="2f707-147">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="2f707-148">Kies **Ja** als u de vervalste afzender wilt toestaan of kies **Nee** om het bericht als vervalste te markeren.</span><span class="sxs-lookup"><span data-stu-id="2f707-148">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="2f707-149">De actie wordt bepaald door het standaard anti-phishingfilter of een aangepast anti-phishingfilter (de standaardinstelling is **bericht verplaatsen naar map Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="2f707-149">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="2f707-150">Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="2f707-150">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Schermafbeelding van de flyout vervalste afzenders en of de afzender toestemming heeft om spoof te geven](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="2f707-152">De kolommen en waarden die u ziet, worden uitgelegd in de volgende lijst:</span><span class="sxs-lookup"><span data-stu-id="2f707-152">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="2f707-153">**Vervalste gebruiker**: het gebruikersaccount waarvan wordt spoofing.</span><span class="sxs-lookup"><span data-stu-id="2f707-153">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="2f707-154">Dit is de afzender van het bericht in het van `5322.From` -adres dat wordt weergegeven in e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="2f707-154">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="2f707-155">De geldigheid van dit adres is niet gecontroleerd op SPF.</span><span class="sxs-lookup"><span data-stu-id="2f707-155">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="2f707-156">Op het tabblad **uw domeinen** bevat de waarde één e-mailadres of als de bron-e-mailserver een spoofing heeft voor meerdere gebruikersaccounts, het bevat **meer dan één** e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="2f707-156">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="2f707-157">Op het tabblad **externe domeinen** bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="2f707-157">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="2f707-158">**Infrastructuur verzenden**: het domein dat is gevonden in een omgekeerde DNS-zoekopdracht (PTR-record) van het IP-adres van de bron-e-mailserver of het IP-adres als de bron geen PTR-record heeft.</span><span class="sxs-lookup"><span data-stu-id="2f707-158">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="2f707-159">Zie [een overzicht van de standaarden voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichten bronnen en afzenders van berichten.</span><span class="sxs-lookup"><span data-stu-id="2f707-159">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="2f707-160">**# van berichten**: het aantal berichten van de verzendende infrastructuur naar uw organisatie die de opgegeven vervalste afzender of afzenders in de afgelopen 30 dagen bevat.</span><span class="sxs-lookup"><span data-stu-id="2f707-160">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="2f707-161">**# van de klachten van gebruikers**: klachten die door uw gebruikers zijn ingediend binnen de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="2f707-161">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="2f707-162">De klachten vormen meestal in de vorm van ongewenste faxberichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f707-162">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="2f707-163">**Verificatie resultaat**: een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2f707-163">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="2f707-164">**Doorgegeven**: de afzender heeft doorsturen van e-mail verificatie gecontroleerd of e-mail verificatie gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="2f707-164">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="2f707-165">**Mislukt**: de afzender is niet gelukt verificatiecontroles voor EOP te verzenden.</span><span class="sxs-lookup"><span data-stu-id="2f707-165">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="2f707-166">**Onbekend**: het resultaat van deze controles is onbekend.</span><span class="sxs-lookup"><span data-stu-id="2f707-166">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="2f707-167">**Beslissings instelling**: geeft aan welke persoon is bepaald of de verzending van de gebruiker spoofing mag maken:</span><span class="sxs-lookup"><span data-stu-id="2f707-167">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="2f707-168">**Beleid voor spoof informatie** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="2f707-168">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="2f707-169">**Beheerder** (handmatig)</span><span class="sxs-lookup"><span data-stu-id="2f707-169">**Admin** (manual)</span></span>

   - <span data-ttu-id="2f707-170">**Laatst weergegeven**: de laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur die de vervalste gebruiker bevat.</span><span class="sxs-lookup"><span data-stu-id="2f707-170">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="2f707-171">**Toegestaan spoofing?**: de waarden die u hier ziet:</span><span class="sxs-lookup"><span data-stu-id="2f707-171">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="2f707-172">**Ja**: berichten van de combinatie van vervalste gebruikers en het verzenden van een infrastructuur zijn toegestaan en worden niet als vervalste e-mail verwerkt.</span><span class="sxs-lookup"><span data-stu-id="2f707-172">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="2f707-173">**Nee**: berichten van de combinatie van vervalste gebruikers en het verzenden van de infrastructuur zijn gemarkeerd als vervalste.</span><span class="sxs-lookup"><span data-stu-id="2f707-173">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="2f707-174">De actie wordt bepaald door het standaard anti-phishingfilter of een aangepast anti-phishingfilter (de standaardinstelling is **bericht verplaatsen naar map Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="2f707-174">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="2f707-175">Zie de volgende sectie voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-175">See the next section for more information.</span></span>

     - <span data-ttu-id="2f707-176">**Sommige gebruikers** (alleen de tabbladen van **uw domein** ): een verzendende infrastructuur is een spoofing voor meerdere gebruikers, waarbij sommige vervalste gebruikers zijn toegestaan en andere niet.</span><span class="sxs-lookup"><span data-stu-id="2f707-176">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="2f707-177">Gebruik het tabblad **gedetailleerd** om de specifieke adressen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2f707-177">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="2f707-178">Klik onder aan de pagina op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2f707-178">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="2f707-179">PowerShell gebruiken voor het beheren van vervalste afzenders</span><span class="sxs-lookup"><span data-stu-id="2f707-179">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="2f707-180">Als u toegestane en geblokkeerde afzenders wilt weergeven in spoof Intelligence, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2f707-180">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="2f707-181">In het volgende voorbeeld wordt gedetailleerde informatie geretourneerd over alle afzenders die zijn toegestaan voor spoofing aan gebruikers in uw domeinen.</span><span class="sxs-lookup"><span data-stu-id="2f707-181">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="2f707-182">Zie [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-182">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="2f707-183">Voer de volgende stappen uit om toegestane en geblokkeerde afzenders te configureren in spoof Intelligence:</span><span class="sxs-lookup"><span data-stu-id="2f707-183">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="2f707-184">De huidige lijst met gedetecteerde vervalste afzenders vastleggen door de uitvoer van de **Get-PhishFilterPolicy** -cmdlet te schrijven naar een CSV-bestand:</span><span class="sxs-lookup"><span data-stu-id="2f707-184">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="2f707-185">Het CSV-bestand bewerken om de **SpoofedUser** (e-mailadres) en **AllowedToSpoof** (ja of Nee) toe te voegen of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2f707-185">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="2f707-186">Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de naam `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="2f707-186">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="2f707-187">Gebruik de `$UpdateSpoofedSenders` variabele om het beleid voor spoof informatie te configureren:</span><span class="sxs-lookup"><span data-stu-id="2f707-187">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="2f707-188">Zie [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2f707-188">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="2f707-189">De beveiligings & voor compliance gebruiken om spoof intelligence te configureren</span><span class="sxs-lookup"><span data-stu-id="2f707-189">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="2f707-190">De configuratieopties voor spoof Intelligence worden beschreven in de [spoofberichten-instellingen in anti phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="2f707-190">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="2f707-191">U kunt instellingen voor spoof Intelligence configureren in het standaard anti-phishingfilter en ook in aangepaste beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="2f707-191">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="2f707-192">Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:</span><span class="sxs-lookup"><span data-stu-id="2f707-192">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="2f707-193">Een [anti-phishing beleid configureren in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-193">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="2f707-194">Een [anti-phishing beleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-194">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2f707-195">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="2f707-195">How do you know these procedures worked?</span></span>

<span data-ttu-id="2f707-196">Voer een van de volgende stappen uit om te controleren of u de gebruikers van de spoof-informatie hebt geconfigureerd met afzenders die zijn toegestaan en die niet zijn toegestaan voor spoofing en dat u de instellingen voor de spoof Intelligence hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="2f707-196">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="2f707-197">Ga in het beveiligings & compliance naar het **beleid voor** het oplossen van beveiligingsfuncties het \> **Policy** \> beleid voor het beleid voor spoofing **-** ondersteuning en selecteer de optie Ik wil \> **Spoof intelligence policy** \> **al gecontroleerde afzenders** \> **Your Domains** **External Domains** **Allowed to spoof?**</span><span class="sxs-lookup"><span data-stu-id="2f707-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="2f707-198">Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die zijn toegestaan en die niet zijn toegestaan voor spoofing:</span><span class="sxs-lookup"><span data-stu-id="2f707-198">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="2f707-199">In PowerShell voert u de volgende opdracht uit om de lijst met alle vervalste afzenders te exporteren naar een CSV-bestand:</span><span class="sxs-lookup"><span data-stu-id="2f707-199">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="2f707-200">Ga op een van de volgende **manieren te werk** in het beveiligings & nalevings centrum \> **Policy** \> : **anti phishing** of **ATP anti phishing** en voer een van de volgende stappen uit:  </span><span class="sxs-lookup"><span data-stu-id="2f707-200">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="2f707-201">Selecteer een beleid in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2f707-201">Select a policy from the list.</span></span> <span data-ttu-id="2f707-202">Controleer in het vervolgmenu dat wordt weergegeven, de waarden in de sectie **spoof** .</span><span class="sxs-lookup"><span data-stu-id="2f707-202">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="2f707-203">Klik op **standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="2f707-203">Click **Default policy**.</span></span> <span data-ttu-id="2f707-204">Controleer in het vervolgmenu dat wordt weergegeven, de waarden in de sectie **spoof** .</span><span class="sxs-lookup"><span data-stu-id="2f707-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="2f707-205">Vervang in Exchange Online PowerShell de \<Name\> optie door Office365 AntiPhish standaard of de naam van een aangepast beleid, en voer de volgende opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="2f707-205">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="2f707-206">Andere manieren om spoofing en phishing te beheren</span><span class="sxs-lookup"><span data-stu-id="2f707-206">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="2f707-207">Wees zeer voor spoofing en phishing bescherming.</span><span class="sxs-lookup"><span data-stu-id="2f707-207">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="2f707-208">Hier zijn een paar manieren om spoofing van afzenders te controleren en om te voorkomen dat ze uw organisatie gevaarlijk kunnen maken:</span><span class="sxs-lookup"><span data-stu-id="2f707-208">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="2f707-209">Controleer het **e-mail rapport voor spoofberichten**.</span><span class="sxs-lookup"><span data-stu-id="2f707-209">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="2f707-210">U kunt dit rapport vaak gebruiken om vervalste afzenders te bekijken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="2f707-210">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="2f707-211">Zie voor meer informatie het [rapport spoofberichten detectie](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="2f707-211">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="2f707-212">Controleer de SPF-configuratie (Sender Policy Framework).</span><span class="sxs-lookup"><span data-stu-id="2f707-212">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="2f707-213">Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-213">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="2f707-214">Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-214">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="2f707-215">Controleer de configuratie van de door DomainKeys geïdentificeerde E-mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="2f707-215">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="2f707-216">U kunt ook DKIM en de DMARC gebruiken om te voorkomen dat hackers berichten verzenden die eruitzien als ze afkomstig zijn van uw domein.</span><span class="sxs-lookup"><span data-stu-id="2f707-216">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="2f707-217">Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="2f707-217">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="2f707-218">Zie voor meer informatie [dkim gebruiken voor het valideren van uitgaande e-mail verzonden vanaf uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-218">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="2f707-219">Controleer de configuratie van berichtverificatie, rapportage en conformiteit van uw domein (DMARC).</span><span class="sxs-lookup"><span data-stu-id="2f707-219">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="2f707-220">De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email.</span><span class="sxs-lookup"><span data-stu-id="2f707-220">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="2f707-221">DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen.</span><span class="sxs-lookup"><span data-stu-id="2f707-221">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="2f707-222">Zie voor meer informatie [het artikel DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="2f707-222">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
