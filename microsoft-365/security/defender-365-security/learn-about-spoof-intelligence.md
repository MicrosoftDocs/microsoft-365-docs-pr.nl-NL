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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over spoof intelligence in Exchange Online Protection (EOP), waar u specifieke vervalste afzenders kunt toestaan of blokkeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058874"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="f5170-103">Spoof intelligence configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="f5170-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f5170-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f5170-104">**Applies to**</span></span>
- [<span data-ttu-id="f5170-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f5170-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f5170-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f5170-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f5170-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5170-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f5170-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beschermd tegen spoofing door EOP.</span><span class="sxs-lookup"><span data-stu-id="f5170-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="f5170-109">EOP gebruikt spoof intelligence als onderdeel van de algehele verdediging van uw organisatie tegen phishing.</span><span class="sxs-lookup"><span data-stu-id="f5170-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="f5170-110">Zie Bescherming tegen spoofing in [EOP voor meer informatie.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f5170-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f5170-111">Wanneer een afzender een e-mailadres vervalst, lijkt deze een gebruiker te zijn in een van de domeinen van uw organisatie of een gebruiker in een extern domein die e-mail naar uw organisatie verzendt.</span><span class="sxs-lookup"><span data-stu-id="f5170-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="f5170-112">Aanvallers die afzenders spoofen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="f5170-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="f5170-113">Maar er zijn scenario's waarin legitieme afzenders spoofing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f5170-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="f5170-114">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="f5170-114">For example:</span></span>

- <span data-ttu-id="f5170-115">Legitieme scenario's voor het vervalsen van interne domeinen:</span><span class="sxs-lookup"><span data-stu-id="f5170-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="f5170-116">Afzenders van derden gebruiken uw domein om bulkmail naar uw eigen werknemers te verzenden voor bedrijfspeilingen.</span><span class="sxs-lookup"><span data-stu-id="f5170-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="f5170-117">Een extern bedrijf genereert en verzendt namens u reclame- of productupdates.</span><span class="sxs-lookup"><span data-stu-id="f5170-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="f5170-118">Een assistent moet regelmatig e-mail verzenden voor een andere persoon binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="f5170-119">Met een interne toepassing worden e-mailmeldingen verzonden.</span><span class="sxs-lookup"><span data-stu-id="f5170-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="f5170-120">Legitieme scenario's voor spoofing van externe domeinen:</span><span class="sxs-lookup"><span data-stu-id="f5170-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="f5170-121">De afzender staat op een adressenlijst (ook wel een discussielijst genoemd) en de adressenlijst geeft e-mail door van de oorspronkelijke afzender naar alle deelnemers op de adressenlijst.</span><span class="sxs-lookup"><span data-stu-id="f5170-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="f5170-122">Een extern bedrijf verzendt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-servicebedrijf).</span><span class="sxs-lookup"><span data-stu-id="f5170-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="f5170-123">Spoof intelligence, en met name het standaardbeleid voor spoof intelligence (en alleen spoof intelligence), helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet wordt meegesnnapt in EOP-spamfilters of externe e-mailsystemen, terwijl uw gebruikers worden beschermd tegen spam- of phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="f5170-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="f5170-124">U kunt spoofinformatie beheren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="f5170-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5170-125">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f5170-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5170-126">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f5170-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f5170-127">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="f5170-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="f5170-128">Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="f5170-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f5170-129">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5170-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f5170-130">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5170-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f5170-131">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="f5170-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f5170-132">Als u het spoof intelligence-beleid wilt wijzigen of spoofinformatie wilt in- of uitschakelen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="f5170-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f5170-133">Voor alleen-lezen toegang tot het spoof intelligence-beleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="f5170-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f5170-134">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-134">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="f5170-135">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="f5170-135">**Notes**:</span></span>

  - <span data-ttu-id="f5170-136">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5170-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f5170-137">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="f5170-138">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="f5170-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f5170-139">Zie Standaardinstellingen voor [anti-phishingbeleid](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)van EOP voor onze aanbevolen instellingen voor spoofinformatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="f5170-140">Het beveiligings- & compliancecentrum gebruiken om vervalste afzenders te beheren</span><span class="sxs-lookup"><span data-stu-id="f5170-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="f5170-141">Als u een Microsoft 365 Enterprise E5-abonnement hebt of afzonderlijk een Microsoft Defender voor Office 365-invoegabonnement hebt gekocht, kunt u ook afzenders beheren die uw domein spoofen via het inzicht in [Spoof Intelligence.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="f5170-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="f5170-142">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="f5170-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f5170-143">Klik op **de pagina Antispam-instellingen** op ![ Pictogram Uitvvllen ](../../media/scc-expand-icon.png) om **spoofintelligentiebeleid uit te vouwen.**</span><span class="sxs-lookup"><span data-stu-id="f5170-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Het spoof intelligence-beleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="f5170-145">Maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="f5170-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="f5170-146">**Nieuwe afzenders controleren**</span><span class="sxs-lookup"><span data-stu-id="f5170-146">**Review new senders**</span></span>
   - <span data-ttu-id="f5170-147">**Laat mij afzenders zien die ik al heb bekeken**</span><span class="sxs-lookup"><span data-stu-id="f5170-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="f5170-148">Selecteer een van de volgende tabbladen in de fly-out Beslissen of deze **afzenders** uw gebruikers mogen spoofen:</span><span class="sxs-lookup"><span data-stu-id="f5170-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="f5170-149">**Uw domeinen:** afzenders die gebruikers spoofen in uw interne domeinen.</span><span class="sxs-lookup"><span data-stu-id="f5170-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="f5170-150">**Externe domeinen:** afzenders die gebruikers spoofen in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="f5170-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="f5170-151">Klik ![ op Pictogram ](../../media/scc-expand-icon.png) Uitv in de kolom **Toegestaan om te** vervalsen?</span><span class="sxs-lookup"><span data-stu-id="f5170-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="f5170-152">Kies **Ja** om de vervalste afzender toe te staan of kies **Nee om** het bericht te markeren als vervalst.</span><span class="sxs-lookup"><span data-stu-id="f5170-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="f5170-153">De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="f5170-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f5170-154">Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Schermafbeelding van de spoofed senders flyout en of de afzender mag spoofen](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="f5170-156">De kolommen en waarden die u ziet, worden in de volgende lijst uitgelegd:</span><span class="sxs-lookup"><span data-stu-id="f5170-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="f5170-157">**Vervalste gebruiker:** het gebruikersaccount dat wordt vervalst.</span><span class="sxs-lookup"><span data-stu-id="f5170-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="f5170-158">Dit is de afzender van het bericht in het Van-adres (ook wel het adres genoemd) dat `5322.From` wordt weergegeven in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="f5170-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="f5170-159">De geldigheid van dit adres wordt niet gecontroleerd door SPF.</span><span class="sxs-lookup"><span data-stu-id="f5170-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="f5170-160">Op het **tabblad Uw** domeinen bevat de waarde één e-mailadres of als de bron-e-mailserver meerdere gebruikersaccounts vervalst, bevat deze meer **dan één**.</span><span class="sxs-lookup"><span data-stu-id="f5170-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="f5170-161">Op het **tabblad Externe** domeinen bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="f5170-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="f5170-162">**Verzendende infrastructuur:** het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="f5170-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="f5170-163">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="f5170-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="f5170-164">Zie Een overzicht van de standaarden voor [e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichtbronnen en afzenders van berichten.</span><span class="sxs-lookup"><span data-stu-id="f5170-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="f5170-165">**# van berichten:** Het aantal berichten van de verzendende infrastructuur naar uw organisatie dat de opgegeven vervalste afzender of afzenders bevat binnen de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="f5170-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="f5170-166">**# van gebruikersklachten:** Klachten die door uw gebruikers zijn ingediend tegen deze afzender binnen de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="f5170-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="f5170-167">Klachten worden meestal in de vorm van ongewenste e-mail ingediend bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5170-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="f5170-168">**Verificatieresultaat:** Een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f5170-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="f5170-169">**Geslaagd:** De afzender heeft de verificatiecontroles voor e-mail van afzenders (SPF of DKIM) doorgegeven.</span><span class="sxs-lookup"><span data-stu-id="f5170-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="f5170-170">**Mislukt:** de afzender heeft de verificatie van EOP-afzenders mislukt.</span><span class="sxs-lookup"><span data-stu-id="f5170-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="f5170-171">**Onbekend:** Het resultaat van deze controles is niet bekend.</span><span class="sxs-lookup"><span data-stu-id="f5170-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="f5170-172">**Beslissing ingesteld door**: Geeft aan wie heeft bepaald of de verzendende infrastructuur de gebruiker mag vervalsen:</span><span class="sxs-lookup"><span data-stu-id="f5170-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="f5170-173">**Spoof intelligence policy** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="f5170-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="f5170-174">**Beheerder** (handmatig)</span><span class="sxs-lookup"><span data-stu-id="f5170-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="f5170-175">**Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met de vervalste gebruiker.</span><span class="sxs-lookup"><span data-stu-id="f5170-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="f5170-176">**Toegestaan om te vervalsen?**: De waarden die u hier ziet, zijn:</span><span class="sxs-lookup"><span data-stu-id="f5170-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="f5170-177">**Ja:** Berichten uit de combinatie van vervalste gebruikers- en verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.</span><span class="sxs-lookup"><span data-stu-id="f5170-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="f5170-178">**Nee:** Berichten uit de combinatie van vervalste gebruikers- en verzendende infrastructuur worden gemarkeerd als vervalst.</span><span class="sxs-lookup"><span data-stu-id="f5170-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="f5170-179">De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="f5170-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f5170-180">Zie de volgende sectie voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-180">See the next section for more information.</span></span>

     - <span data-ttu-id="f5170-181">**Sommige gebruikers** **(alleen het** tabblad Domeinen): Een verzendende infrastructuur is een spoofing van meerdere gebruikers, waarbij sommige vervalste gebruikers zijn toegestaan en andere niet.</span><span class="sxs-lookup"><span data-stu-id="f5170-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="f5170-182">Gebruik het **tabblad Gedetailleerd** om de specifieke adressen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f5170-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="f5170-183">Klik onder aan de pagina op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="f5170-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="f5170-184">PowerShell gebruiken om vervalste afzenders te beheren</span><span class="sxs-lookup"><span data-stu-id="f5170-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="f5170-185">Gebruik de volgende syntaxis om toegestane en geblokkeerde afzenders weer te geven in spoof intelligence:</span><span class="sxs-lookup"><span data-stu-id="f5170-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="f5170-186">Dit voorbeeld retourneert gedetailleerde informatie over alle afzenders die gebruikers in uw domeinen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="f5170-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="f5170-187">Zie [Get-PhishFilterPolicy (Get-PhishFilterPolicy)](/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f5170-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="f5170-188">Als u toegestane en geblokkeerde afzenders wilt configureren in spoofinformatie, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="f5170-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="f5170-189">Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de **cmdlet Get-PhishFilterPolicy** te schrijven naar een CSV-bestand:</span><span class="sxs-lookup"><span data-stu-id="f5170-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="f5170-190">Bewerk het CSV-bestand om de **waarden SpoofedUser** (e-mailadres) en **AllowedToSpoof** (Ja of Nee) toe te voegen of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f5170-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="f5170-191">Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de naam `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="f5170-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="f5170-192">Gebruik de `$UpdateSpoofedSenders` variabele om het spoof intelligence-beleid te configureren:</span><span class="sxs-lookup"><span data-stu-id="f5170-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="f5170-193">Zie [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f5170-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="f5170-194">Gebruik het Beveiligings- & compliancecentrum om spoofinformatie te configureren</span><span class="sxs-lookup"><span data-stu-id="f5170-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="f5170-195">De configuratieopties voor spoofinformatie worden beschreven in [spoofinstellingen in anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="f5170-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f5170-196">U kunt spoof intelligence-instellingen configureren in het standaard anti-phishingbeleid en ook in aangepast beleid.</span><span class="sxs-lookup"><span data-stu-id="f5170-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="f5170-197">Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:</span><span class="sxs-lookup"><span data-stu-id="f5170-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="f5170-198">[Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f5170-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="f5170-199">[Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f5170-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f5170-200">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="f5170-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="f5170-201">Gebruik een van de volgende stappen om te controleren of u spoofinformatie hebt geconfigureerd met afzenders die wel en niet mogen spoofen en of u de instellingen voor spoof intelligence hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="f5170-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="f5170-202">Ga in het beveiligings- & compliancecentrum naar Beleid voor bedreigingsbeheer  \>  \> **Antispam** \>  \>  \>    uitvbreed spoofinformatiebeleid selecteer Mij afzenders laten zien die ik al heb bekeken, selecteer het tabblad Uw domeinen of Externe domeinen en controleer de waarde Toegestaan om te spoofen? voor de afzender.</span><span class="sxs-lookup"><span data-stu-id="f5170-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="f5170-203">Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die wel en niet mogen spoofen:</span><span class="sxs-lookup"><span data-stu-id="f5170-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="f5170-204">Voer in PowerShell de volgende opdracht uit om de lijst met alle vervalste afzenders te exporteren naar een CSV-bestand:</span><span class="sxs-lookup"><span data-stu-id="f5170-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="f5170-205">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **Anti-phishing** of **ATP anti-phishing** en ga naar een van de volgende stappen:  </span><span class="sxs-lookup"><span data-stu-id="f5170-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="f5170-206">Selecteer een beleid in de lijst.</span><span class="sxs-lookup"><span data-stu-id="f5170-206">Select a policy from the list.</span></span> <span data-ttu-id="f5170-207">Controleer in het flyout dat wordt weergegeven de waarden in de **sectie Spoof.**</span><span class="sxs-lookup"><span data-stu-id="f5170-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="f5170-208">Klik **op Standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="f5170-208">Click **Default policy**.</span></span> <span data-ttu-id="f5170-209">Controleer in het flyout dat wordt weergegeven de waarden in de **sectie Spoof.**</span><span class="sxs-lookup"><span data-stu-id="f5170-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="f5170-210">Vervang in Exchange Online PowerShell \<Name\> door Office365 AntiPhish Default of de naam van een aangepast beleid en voer de volgende opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="f5170-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="f5170-211">Andere manieren om spoofing en phishing te beheren</span><span class="sxs-lookup"><span data-stu-id="f5170-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="f5170-212">Wees zorgvuldig met spoofing en phishingbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="f5170-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="f5170-213">Hier zijn verwante manieren om te controleren of afzenders uw domein vervalsen en te voorkomen dat ze uw organisatie beschadigen:</span><span class="sxs-lookup"><span data-stu-id="f5170-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="f5170-214">Controleer het **spoof-e-mailrapport.**</span><span class="sxs-lookup"><span data-stu-id="f5170-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="f5170-215">U kunt dit rapport vaak gebruiken om vervalste afzenders weer te geven en te beheren.</span><span class="sxs-lookup"><span data-stu-id="f5170-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="f5170-216">Zie Rapport [Spoofdetecties voor meer informatie.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f5170-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="f5170-217">Controleer de SPF-configuratie (Sender Policy Framework).</span><span class="sxs-lookup"><span data-stu-id="f5170-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="f5170-218">Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f5170-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="f5170-219">Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f5170-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="f5170-220">Controleer de DKIM-configuratie (DomainKeys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="f5170-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="f5170-221">U moet DKIM naast SPF en DMARC gebruiken om te voorkomen dat aanvallers berichten verzenden die eruit zien alsof ze afkomstig zijn van uw domein.</span><span class="sxs-lookup"><span data-stu-id="f5170-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="f5170-222">Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="f5170-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="f5170-223">Zie DKIM gebruiken om uitgaande e-mail te valideren die is verzonden vanuit uw [aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="f5170-224">Controleer uw DMARC-configuratie (Domain-based Message Authentication, Reporting, and Conformance).</span><span class="sxs-lookup"><span data-stu-id="f5170-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="f5170-225">De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email.</span><span class="sxs-lookup"><span data-stu-id="f5170-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="f5170-226">DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen.</span><span class="sxs-lookup"><span data-stu-id="f5170-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="f5170-227">Zie [DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f5170-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>