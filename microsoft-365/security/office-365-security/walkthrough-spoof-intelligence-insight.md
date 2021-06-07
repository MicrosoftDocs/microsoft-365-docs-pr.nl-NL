---
title: Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze het spoof intelligence-beleid en het inzicht in spoof intelligence kunnen gebruiken om gedetecteerde vervalste afzenders toe te staan of te blokkeren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793206"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="d4f36-103">Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof intelligence in EOP</span><span class="sxs-lookup"><span data-stu-id="d4f36-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d4f36-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d4f36-104">**Applies to**</span></span>
- [<span data-ttu-id="d4f36-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d4f36-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d4f36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4f36-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="d4f36-107">In dit artikel wordt beschreven welke oudere, vervalste afzenderbeheerervaring wordt vervangen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="d4f36-108">Zie Inzicht in spoof [intelligence in EOP](learn-about-spoof-intelligence.md) voor meer informatie over de nieuwe ervaring</span><span class="sxs-lookup"><span data-stu-id="d4f36-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="d4f36-109">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beschermd tegen spoofing door EOP.</span><span class="sxs-lookup"><span data-stu-id="d4f36-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="d4f36-110">EOP gebruikt **spoof intelligence** als onderdeel van de algehele verdediging van uw organisatie tegen phishing.</span><span class="sxs-lookup"><span data-stu-id="d4f36-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="d4f36-111">Zie Bescherming tegen spoofing in [EOP voor meer informatie.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d4f36-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="d4f36-112">Het standaardbeleid voor spoof intelligence (en alleen spoof **intelligence)** helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet in de EOP-spamfilters terecht komt en dat uw gebruikers worden beschermd tegen spam- of phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="d4f36-113">U kunt ook het inzicht in **spoofinformatie** gebruiken om snel te bepalen welke externe afzenders u legitiem niet-genauteerde e-mail sturen (berichten uit domeinen die niet door SPF-, DKIM- of DMARC-controles worden verzonden).</span><span class="sxs-lookup"><span data-stu-id="d4f36-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="d4f36-114">U kunt spoofinformatie beheren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="d4f36-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d4f36-115">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d4f36-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d4f36-116">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d4f36-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="d4f36-117">Als u rechtstreeks naar de **pagina Anti-spaminstellingen voor** het spoof intelligence-beleid wilt gaan, gebruikt u <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="d4f36-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="d4f36-118">Als u rechtstreeks naar de pagina **Beveiligingsdashboard wilt** gaan voor het inzicht in spoof intelligence, gebruikt <https://protection.office.com/searchandinvestigation/dashboard> u .</span><span class="sxs-lookup"><span data-stu-id="d4f36-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="d4f36-119">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4f36-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d4f36-120">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4f36-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d4f36-121">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d4f36-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d4f36-122">Als u het spoof intelligence-beleid wilt wijzigen of spoofinformatie wilt in- of uitschakelen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="d4f36-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d4f36-123">Voor alleen-lezen toegang tot het spoof intelligence-beleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="d4f36-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d4f36-124">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4f36-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="d4f36-125">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d4f36-125">**Notes**:</span></span>

  - <span data-ttu-id="d4f36-126">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f36-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d4f36-127">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4f36-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d4f36-128">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="d4f36-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="d4f36-129">De opties voor spoofinformatie worden beschreven in [spoofinstellingen in anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="d4f36-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="d4f36-130">U kunt de instellingen voor spoof intelligence inschakelen, uitschakelen en configureren in anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="d4f36-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="d4f36-131">Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:</span><span class="sxs-lookup"><span data-stu-id="d4f36-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="d4f36-132">[Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d4f36-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="d4f36-133">[Anti-phishingbeleid configureren in Microsoft Defender voor Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d4f36-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="d4f36-134">Zie [EOP anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor spoofinformatie.</span><span class="sxs-lookup"><span data-stu-id="d4f36-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="d4f36-135">Vervalste afzenders beheren</span><span class="sxs-lookup"><span data-stu-id="d4f36-135">Manage spoofed senders</span></span>

<span data-ttu-id="d4f36-136">Er zijn twee manieren om vervalste afzenders toe te staan en te blokkeren:</span><span class="sxs-lookup"><span data-stu-id="d4f36-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="d4f36-137">Het spoof intelligence-beleid gebruiken</span><span class="sxs-lookup"><span data-stu-id="d4f36-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="d4f36-138">Het inzicht in spoof intelligence gebruiken</span><span class="sxs-lookup"><span data-stu-id="d4f36-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="d4f36-139">Vervalste afzenders beheren in het beleid voor spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="d4f36-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="d4f36-140">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="d4f36-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d4f36-141">Klik op **de pagina Antispam-instellingen** op ![ Pictogram Uitvvllen ](../../media/scc-expand-icon.png) om **spoofintelligentiebeleid uit te vouwen.**</span><span class="sxs-lookup"><span data-stu-id="d4f36-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Het spoof intelligence-beleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="d4f36-143">Maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="d4f36-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="d4f36-144">**Nieuwe afzenders controleren**</span><span class="sxs-lookup"><span data-stu-id="d4f36-144">**Review new senders**</span></span>
   - <span data-ttu-id="d4f36-145">**Laat mij afzenders zien die ik al heb bekeken**</span><span class="sxs-lookup"><span data-stu-id="d4f36-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="d4f36-146">Selecteer een van de volgende tabbladen in de fly-out Beslissen of deze **afzenders** uw gebruikers mogen spoofen:</span><span class="sxs-lookup"><span data-stu-id="d4f36-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="d4f36-147">**Uw domeinen:** afzenders die gebruikers spoofen in uw interne domeinen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="d4f36-148">**Externe domeinen:** afzenders die gebruikers spoofen in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="d4f36-149">Klik ![ op Pictogram ](../../media/scc-expand-icon.png) Uitv in de kolom **Toegestaan om te** vervalsen?</span><span class="sxs-lookup"><span data-stu-id="d4f36-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="d4f36-150">Kies **Ja** om de vervalste afzender toe te staan of kies **Nee om** het bericht te markeren als vervalst.</span><span class="sxs-lookup"><span data-stu-id="d4f36-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="d4f36-151">De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="d4f36-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="d4f36-152">Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4f36-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Schermafbeelding van de spoofed senders flyout en of de afzender mag spoofen](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="d4f36-154">De kolommen en waarden die u ziet, worden in de volgende lijst uitgelegd:</span><span class="sxs-lookup"><span data-stu-id="d4f36-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="d4f36-155">**Vervalste gebruiker:** het gebruikersaccount dat wordt vervalst.</span><span class="sxs-lookup"><span data-stu-id="d4f36-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="d4f36-156">Dit is de afzender van het bericht in het Van-adres (ook wel het adres genoemd) dat `5322.From` wordt weergegeven in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="d4f36-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="d4f36-157">De geldigheid van dit adres wordt niet gecontroleerd door SPF.</span><span class="sxs-lookup"><span data-stu-id="d4f36-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="d4f36-158">Op het **tabblad Uw** domeinen bevat de waarde één e-mailadres of als de bron-e-mailserver meerdere gebruikersaccounts vervalst, bevat deze meer **dan één**.</span><span class="sxs-lookup"><span data-stu-id="d4f36-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="d4f36-159">Op het **tabblad Externe** domeinen bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="d4f36-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="d4f36-160">**Verzendende infrastructuur:** het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="d4f36-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="d4f36-161">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="d4f36-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="d4f36-162">Zie Een overzicht van de standaarden voor [e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichtbronnen en afzenders van berichten.</span><span class="sxs-lookup"><span data-stu-id="d4f36-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="d4f36-163">**# van berichten:** Het aantal berichten van de verzendende infrastructuur naar uw organisatie dat de opgegeven vervalste afzender of afzenders bevat binnen de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="d4f36-164">**# van gebruikersklachten:** Klachten die door uw gebruikers zijn ingediend tegen deze afzender binnen de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="d4f36-165">Klachten worden meestal in de vorm van ongewenste e-mail ingediend bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4f36-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="d4f36-166">**Verificatieresultaat:** Een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d4f36-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="d4f36-167">**Geslaagd:** De afzender heeft de verificatiecontroles voor e-mail van afzenders (SPF of DKIM) doorgegeven.</span><span class="sxs-lookup"><span data-stu-id="d4f36-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="d4f36-168">**Mislukt:** de afzender heeft de verificatie van EOP-afzenders mislukt.</span><span class="sxs-lookup"><span data-stu-id="d4f36-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="d4f36-169">**Onbekend:** Het resultaat van deze controles is niet bekend.</span><span class="sxs-lookup"><span data-stu-id="d4f36-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="d4f36-170">**Beslissing ingesteld door**: Geeft aan wie heeft bepaald of de verzendende infrastructuur de gebruiker mag vervalsen:</span><span class="sxs-lookup"><span data-stu-id="d4f36-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="d4f36-171">**Spoof intelligence policy** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="d4f36-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="d4f36-172">**Beheerder** (handmatig)</span><span class="sxs-lookup"><span data-stu-id="d4f36-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="d4f36-173">**Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met de vervalste gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d4f36-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="d4f36-174">**Toegestaan om te vervalsen?**: De waarden die u hier ziet, zijn:</span><span class="sxs-lookup"><span data-stu-id="d4f36-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="d4f36-175">**Ja:** Berichten uit de combinatie van vervalste gebruikers- en verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.</span><span class="sxs-lookup"><span data-stu-id="d4f36-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="d4f36-176">**Nee:** Berichten uit de combinatie van vervalste gebruikers- en verzendende infrastructuur worden gemarkeerd als vervalst.</span><span class="sxs-lookup"><span data-stu-id="d4f36-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="d4f36-177">De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="d4f36-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="d4f36-178">Zie de volgende sectie voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d4f36-178">See the next section for more information.</span></span>

     - <span data-ttu-id="d4f36-179">**Sommige gebruikers** **(alleen het** tabblad Domeinen): Een verzendende infrastructuur is een spoofing van meerdere gebruikers, waarbij sommige vervalste gebruikers zijn toegestaan en andere niet.</span><span class="sxs-lookup"><span data-stu-id="d4f36-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="d4f36-180">Gebruik het **tabblad Gedetailleerd** om de specifieke adressen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d4f36-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="d4f36-181">Klik onder aan de pagina op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="d4f36-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="d4f36-182">PowerShell gebruiken om vervalste afzenders te beheren</span><span class="sxs-lookup"><span data-stu-id="d4f36-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="d4f36-183">Gebruik de volgende syntaxis om toegestane en geblokkeerde afzenders weer te geven in spoof intelligence:</span><span class="sxs-lookup"><span data-stu-id="d4f36-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="d4f36-184">Dit voorbeeld retourneert gedetailleerde informatie over alle afzenders die gebruikers in uw domeinen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="d4f36-185">Zie [Get-PhishFilterPolicy (Get-PhishFilterPolicy)](/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d4f36-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="d4f36-186">Als u toegestane en geblokkeerde afzenders wilt configureren in spoofinformatie, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d4f36-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="d4f36-187">Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de **cmdlet Get-PhishFilterPolicy** te schrijven naar een CSV-bestand door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="d4f36-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="d4f36-188">Bewerk het CSV-bestand om de volgende waarden toe te voegen of te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="d4f36-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="d4f36-189">**Afzender** (domein in de PTR-record of IP/24-adres van de bronserver)</span><span class="sxs-lookup"><span data-stu-id="d4f36-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="d4f36-190">**SpoofedUser:** Een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d4f36-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="d4f36-191">Het e-mailadres van de interne gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d4f36-191">The internal user's email address.</span></span>
     - <span data-ttu-id="d4f36-192">Het e-maildomein van de externe gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d4f36-192">The external user's email domain.</span></span>
     - <span data-ttu-id="d4f36-193">Een lege waarde die aangeeft dat u alle vervalste berichten van de opgegeven afzender wilt blokkeren of **toestaan,** ongeacht het vervalste e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="d4f36-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="d4f36-194">**AllowedToSpoof** (Ja of Nee)</span><span class="sxs-lookup"><span data-stu-id="d4f36-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="d4f36-195">**SpoofType** (intern of extern)</span><span class="sxs-lookup"><span data-stu-id="d4f36-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="d4f36-196">Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de volgende `$UpdateSpoofedSenders` opdracht:</span><span class="sxs-lookup"><span data-stu-id="d4f36-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="d4f36-197">Gebruik de `$UpdateSpoofedSenders` variabele om het spoof intelligence-beleid te configureren door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="d4f36-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="d4f36-198">Zie [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="d4f36-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="d4f36-199">Vervalste afzenders beheren in het inzicht in spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="d4f36-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="d4f36-200">Ga in het & Compliancecentrum naar **Threat Management** \> **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="d4f36-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="d4f36-201">Zoek in **de rij** Inzichten naar een van de volgende items:</span><span class="sxs-lookup"><span data-stu-id="d4f36-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="d4f36-202">**Waarschijnlijk vervalste domeinen in** de afgelopen zeven dagen: Dit inzicht geeft aan dat spoof intelligence is ingeschakeld (deze is standaard ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="d4f36-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="d4f36-203">**Spoofbeveiliging inschakelen:** dit inzicht geeft aan dat spoofinformatie is uitgeschakeld en als u op het inzicht klikt, kunt u spoofinformatie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="d4f36-204">In het inzicht op het dashboard ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="d4f36-204">The insight on the dashboard shows you information like this:</span></span>

   ![Schermafbeelding van inzicht in spoof intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="d4f36-206">Dit inzicht heeft twee modi:</span><span class="sxs-lookup"><span data-stu-id="d4f36-206">This insight has two modes:</span></span>

   - <span data-ttu-id="d4f36-207">**Insight-modus:** als spoof intelligence is ingeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="d4f36-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="d4f36-208">**Wat als de modus**: Als spoof intelligence is  uitgeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="d4f36-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="d4f36-209">Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, zijn onderverdeeld in twee categorieën: **Verdachte** domeinen en **Niet-verdachte domeinen.**</span><span class="sxs-lookup"><span data-stu-id="d4f36-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="d4f36-210">**Verdachte domeinen:**</span><span class="sxs-lookup"><span data-stu-id="d4f36-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="d4f36-211">**Spoof** met veel vertrouwen: op basis van de historische verzendingspatronen en de reputatiescore van de domeinen, zijn we ervan overtuigd dat de domeinen spoofing zijn en dat berichten uit deze domeinen waarschijnlijk schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d4f36-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="d4f36-212">**Matig vertrouwen spoof:** Op basis van historische verzendende patronen en de reputatiescore van de domeinen, zijn we er redelijk zeker van dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn.</span><span class="sxs-lookup"><span data-stu-id="d4f36-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="d4f36-213">False positives zijn waarschijnlijker in deze categorie dan spoof met veel vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="d4f36-214">**Niet-verdachte domeinen:** het domein is mislukt expliciete e-mailverificatie [controleert SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="d4f36-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="d4f36-215">Het domein is echter geslaagd voor onze impliciete e-mailverificatiecontroles[(samengestelde verificatie).](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="d4f36-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="d4f36-216">Hierdoor is er geen anti-spoofing actie ondernomen op het bericht.</span><span class="sxs-lookup"><span data-stu-id="d4f36-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="d4f36-217">Gedetailleerde informatie weergeven over verdachte en niet-gunstige domeinen</span><span class="sxs-lookup"><span data-stu-id="d4f36-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="d4f36-218">Klik op de informatie over spoofinformatie op **Verdachte domeinen** of **Niet-verdachte** domeinen om naar de pagina Inzicht in **spoofinformatie te** gaan.</span><span class="sxs-lookup"><span data-stu-id="d4f36-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="d4f36-219">De **pagina Spoof Intelligence Insight** bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="d4f36-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="d4f36-220">**Vervalst domein:** het domein van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients.</span><span class="sxs-lookup"><span data-stu-id="d4f36-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="d4f36-221">Dit adres wordt ook wel het adres `5322.From` genoemd.</span><span class="sxs-lookup"><span data-stu-id="d4f36-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="d4f36-222">**Infrastructuur:** ook wel de _verzendende infrastructuur genoemd._</span><span class="sxs-lookup"><span data-stu-id="d4f36-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="d4f36-223">Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="d4f36-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="d4f36-224">Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="d4f36-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="d4f36-225">**Aantal berichten:** het aantal berichten van de verzendende infrastructuur naar uw organisatie dat het opgegeven vervalste domein bevat in de afgelopen 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="d4f36-226">**Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met het vervalste domein.</span><span class="sxs-lookup"><span data-stu-id="d4f36-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="d4f36-227">**Type spoof:** deze waarde is **Extern**.</span><span class="sxs-lookup"><span data-stu-id="d4f36-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="d4f36-228">**Toegestaan om te vervalsen?**: De waarden die u hier ziet, zijn:</span><span class="sxs-lookup"><span data-stu-id="d4f36-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="d4f36-229">**Ja:** Berichten uit de combinatie van het domein van de vervalste gebruiker en de verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.</span><span class="sxs-lookup"><span data-stu-id="d4f36-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="d4f36-230">**Nee:** Berichten uit de combinatie van het domein van de vervalste gebruiker en de verzendende infrastructuur worden gemarkeerd als vervalst.</span><span class="sxs-lookup"><span data-stu-id="d4f36-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="d4f36-231">De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="d4f36-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="d4f36-232">Selecteer een item in de lijst om details over het domein/verzendende infrastructuurpaar in een flyout weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d4f36-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="d4f36-233">De informatie omvat:</span><span class="sxs-lookup"><span data-stu-id="d4f36-233">The information includes:</span></span>
   - <span data-ttu-id="d4f36-234">Waarom we dit hebben gesnapt.</span><span class="sxs-lookup"><span data-stu-id="d4f36-234">Why we caught this.</span></span>
   - <span data-ttu-id="d4f36-235">Wat u moet doen.</span><span class="sxs-lookup"><span data-stu-id="d4f36-235">What you need to do.</span></span>
   - <span data-ttu-id="d4f36-236">Een domeinoverzicht.</span><span class="sxs-lookup"><span data-stu-id="d4f36-236">A domain summary.</span></span>
   - <span data-ttu-id="d4f36-237">WhoIs-gegevens over de afzender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="d4f36-238">Soortgelijke berichten die we hebben gezien in uw tenant van dezelfde afzender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="d4f36-239">Hier kunt u er ook voor kiezen om het domein-/verzendende infrastructuurpaar toe te voegen of te verwijderen uit de **lijst Toegestane** afzender voor spoofing.</span><span class="sxs-lookup"><span data-stu-id="d4f36-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="d4f36-240">Stel de schakelaar dienovereenkomstig in.</span><span class="sxs-lookup"><span data-stu-id="d4f36-240">Simply set the toggle accordingly.</span></span>

   ![Schermafbeelding van een domein in het deelvenster Informatie over spoofinformatie](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d4f36-242">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="d4f36-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="d4f36-243">Als u wilt controleren of u spoofinformatie hebt geconfigureerd met afzenders die wel en niet mogen spoofen, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="d4f36-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="d4f36-244">Ga in het beveiligings- & compliancecentrum naar Beleid voor bedreigingsbeheer  \>  \> **Antispam** \>  \>  \>    uitvbreed spoofinformatiebeleid selecteer Mij afzenders laten zien die ik al heb bekeken, selecteer het tabblad Uw domeinen of Externe domeinen en controleer de waarde Toegestaan om te spoofen? voor de afzender.</span><span class="sxs-lookup"><span data-stu-id="d4f36-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="d4f36-245">Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die wel en niet mogen spoofen:</span><span class="sxs-lookup"><span data-stu-id="d4f36-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="d4f36-246">Voer in PowerShell de volgende opdracht uit om de lijst met alle vervalste afzenders te exporteren naar een CSV-bestand:</span><span class="sxs-lookup"><span data-stu-id="d4f36-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
