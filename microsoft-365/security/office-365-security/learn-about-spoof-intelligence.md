---
title: Spoofberichten configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u vervalste afzenders configureren om al dan niet toe te staan, en andere instellingen voor spoofinformatie in Exchange Online en Exchange Online Protection (EOP).
ms.openlocfilehash: 958f27d190748ee12976a6b47794a23e025172cf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630489"
---
# <a name="configure-spoof-intelligence-in-microsoft-365"></a><span data-ttu-id="e39b5-103">Spoofintelligentie configureren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e39b5-103">Configure spoof intelligence in Microsoft 365</span></span>

<span data-ttu-id="e39b5-104">Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection (EOP)-klant zonder Exchange Online-postvakken, worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beveiligd tegen spoofing door EOP.</span><span class="sxs-lookup"><span data-stu-id="e39b5-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="e39b5-105">EOP maakt gebruik van spoofintelligentie als onderdeel van de algehele verdediging van uw organisatie tegen phishing.</span><span class="sxs-lookup"><span data-stu-id="e39b5-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="e39b5-106">Zie [Bescherming tegen spoofing in Microsoft 365](anti-spoofing-protection.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-106">For more information, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e39b5-107">Wanneer een afzender een e-mailadres vervalst, lijkt dit een gebruiker te zijn in een van de domeinen van uw organisatie of een gebruiker in een extern domein dat e-mail naar uw organisatie verzendt.</span><span class="sxs-lookup"><span data-stu-id="e39b5-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="e39b5-108">Aanvallers die afzenders spoofen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="e39b5-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="e39b5-109">Maar er zijn scenario's waar legitieme afzenders zijn spoofing.</span><span class="sxs-lookup"><span data-stu-id="e39b5-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="e39b5-110">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e39b5-110">For example:</span></span>

- <span data-ttu-id="e39b5-111">Legitieme scenario's voor het vervalsen van interne domeinen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="e39b5-112">Afzenders van derden gebruiken uw domein om bulkmail naar uw eigen werknemers te sturen voor bedrijfspeilingen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="e39b5-113">Een extern bedrijf genereert en verzendt namens u reclame- of productupdates.</span><span class="sxs-lookup"><span data-stu-id="e39b5-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="e39b5-114">Een assistent moet regelmatig e-mail sturen voor een andere persoon binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="e39b5-115">Een interne toepassing verzendt e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="e39b5-116">Legitieme scenario's voor het vervalsen van externe domeinen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="e39b5-117">De afzender staat op een mailinglijst (ook wel een discussielijst genoemd) en de mailinglijst stuurt e-mail van de oorspronkelijke afzender door aan alle deelnemers op de mailinglijst.</span><span class="sxs-lookup"><span data-stu-id="e39b5-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="e39b5-118">Een extern bedrijf stuurt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-service bedrijf).</span><span class="sxs-lookup"><span data-stu-id="e39b5-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="e39b5-119">Spoofinformatie, en met name het standaard -informatiebeleid (en alleen) spoofintelligentie, helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet verstrikt raakt in spamfilters in Microsoft 365 of externe e-mailsystemen, terwijl uw gebruikers worden beschermd tegen spam of phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in spam filters in Microsoft 365 or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="e39b5-120">U spoofinformatie beheren in het Microsoft 365 Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).</span><span class="sxs-lookup"><span data-stu-id="e39b5-120">You can manage spoof intelligence in the Microsoft 365 Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e39b5-121">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e39b5-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e39b5-122">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e39b5-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e39b5-123">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="e39b5-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="e39b5-124">Gebruik . **Anti-phishing** <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="e39b5-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="e39b5-125">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e39b5-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e39b5-126">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e39b5-126">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e39b5-127">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e39b5-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="e39b5-128">Als u het spoofinformatiebeleid wilt wijzigen of spoofinformatie wilt inschakelen of uitschakelen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="e39b5-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="e39b5-129">Voor alleen-lezen toegang tot het spoof-informatiebeleid moet u lid zijn van de rolgroep **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="e39b5-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="e39b5-130">Zie [Machtigingen in het Office 365-beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="e39b5-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e39b5-131">Voor onze aanbevolen instellingen voor spoofinformatie, [eop standaard anti-phishing beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="e39b5-131">For our recommended settings for spoof intelligence, [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="e39b5-132">Het Beveiligings& Compliance Center gebruiken om vervalste afzenders te beheren</span><span class="sxs-lookup"><span data-stu-id="e39b5-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="e39b5-133">Als u een Office 365 Enterprise E5-abonnement hebt of een afzonderlijk aangeschafte ATP-add-on (Advanced Threat Protection) hebt, u ook afzenders beheren die uw domein spoofen via het [Spoof Intelligence-inzicht.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="e39b5-133">If you have an Office 365 Enterprise E5 subscription or have separately purchased and Advanced Threat Protection (ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="e39b5-134">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="e39b5-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e39b5-135">Klik op de pagina **Antispam-instellingen** op ![Pictogram](../../media/scc-expand-icon.png) Uitvouwen om het **informatiebeleid voor spoofen**uit te vouwen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Het spoof-informatiebeleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="e39b5-137">Maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="e39b5-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="e39b5-138">**Nieuwe afzenders bekijken**</span><span class="sxs-lookup"><span data-stu-id="e39b5-138">**Review new senders**</span></span>
   - <span data-ttu-id="e39b5-139">**Mij afzenders laten zien die ik al heb beoordeeld**</span><span class="sxs-lookup"><span data-stu-id="e39b5-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="e39b5-140">Selecteer een van de volgende tabbladen in de **optie-knop Om te bepalen of deze afzenders uw gebruikersflyout mogen spoofen** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e39b5-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="e39b5-141">**Uw domeinen:** afzenders spoofing gebruikers in uw interne domeinen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="e39b5-142">**Externe domeinen:** afzenders spoofing gebruikers in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="e39b5-143">Klik ![op](../../media/scc-expand-icon.png) Pictogram Uitvouwen in de kolom **Mag spoofen?**</span><span class="sxs-lookup"><span data-stu-id="e39b5-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="e39b5-144">Kies **Ja** om de vervalste afzender toe te staan of kies **Nee** om het bericht als vervalst te markeren.</span><span class="sxs-lookup"><span data-stu-id="e39b5-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="e39b5-145">De actie wordt beheerd door het standaard antiphishingbeleid of het aangepaste ATP-antiphishingbeleid (de standaardwaarde is **Bericht verplaatsen naar ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="e39b5-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="e39b5-146">Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Schermafbeelding van de flyout van vervalste afzenders en of de afzender mag spoofen](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="e39b5-148">De kolommen en waarden die u ziet, worden uitgelegd in de volgende lijst:</span><span class="sxs-lookup"><span data-stu-id="e39b5-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="e39b5-149">**Vervalste gebruiker**: het gebruikersaccount dat wordt vervalst.</span><span class="sxs-lookup"><span data-stu-id="e39b5-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="e39b5-150">Dit is de afzender van het bericht `5322.From` in het Van-adres (ook wel het adres genoemd) dat wordt weergegeven in e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="e39b5-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="e39b5-151">De geldigheid van dit adres wordt niet gecontroleerd door SPF.</span><span class="sxs-lookup"><span data-stu-id="e39b5-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="e39b5-152">Op het tabblad **Uw domeinen** bevat de waarde één e-mailadres of als de bron-e-mailserver meerdere gebruikersaccounts vervalst, bevat deze meer **dan één**.</span><span class="sxs-lookup"><span data-stu-id="e39b5-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="e39b5-153">Op het tabblad **Externe domeinen** bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="e39b5-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="e39b5-154">**Infrastructuur verzenden:** het domein in een reverse DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver of het IP-adres als de bron geen PTR-record heeft.</span><span class="sxs-lookup"><span data-stu-id="e39b5-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="e39b5-155">Zie Een overzicht van de normen [voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichtbronnen en afzenders van berichten.</span><span class="sxs-lookup"><span data-stu-id="e39b5-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="e39b5-156">**aantal berichten:** het aantal berichten van de verzendende infrastructuur naar uw organisatie die de opgegeven vervalste afzender of afzenders bevatten in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="e39b5-157">**# van de klachten van gebruikers**: Klachten ingediend door uw gebruikers tegen deze afzender in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="e39b5-158">Klachten zijn meestal in de vorm van ongewenste inzendingen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e39b5-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="e39b5-159">**Verificatieresultaat:** een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="e39b5-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="e39b5-160">**Geslaagd**: De afzender heeft e-mailverificatiecontroles (SPF of DKIM) door de afzender doorgegeven.</span><span class="sxs-lookup"><span data-stu-id="e39b5-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="e39b5-161">**Mislukt:** de verificatiecontroles van de afzender is mislukt voor eop-afzenders.</span><span class="sxs-lookup"><span data-stu-id="e39b5-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="e39b5-162">**Onbekend**: Het resultaat van deze controles is niet bekend.</span><span class="sxs-lookup"><span data-stu-id="e39b5-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="e39b5-163">**Beslissing ingesteld door**: Geeft aan wie heeft bepaald of de verzendende infrastructuur de gebruiker mag spoofen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="e39b5-164">**Spoofintelligentiebeleid** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="e39b5-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="e39b5-165">**Beheerder** (handleiding)</span><span class="sxs-lookup"><span data-stu-id="e39b5-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="e39b5-166">**Laatst gezien**: de laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur die de vervalste gebruiker bevat.</span><span class="sxs-lookup"><span data-stu-id="e39b5-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="e39b5-167">**Toegestaan om te spoofen?**: De waarden die je hier ziet zijn:</span><span class="sxs-lookup"><span data-stu-id="e39b5-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="e39b5-168">**Ja:** Berichten van de combinatie van vervalste gebruiker en verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.</span><span class="sxs-lookup"><span data-stu-id="e39b5-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="e39b5-169">**Nee:** Berichten van de combinatie van vervalste gebruiker en verzendende infrastructuur zijn gemarkeerd als vervalst.</span><span class="sxs-lookup"><span data-stu-id="e39b5-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="e39b5-170">De actie wordt beheerd door het standaard antiphishingbeleid of het aangepaste ATP-antiphishingbeleid (de standaardwaarde is **Bericht verplaatsen naar ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="e39b5-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="e39b5-171">Zie de volgende sectie voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-171">See the next section for more information.</span></span>

     - <span data-ttu-id="e39b5-172">**Sommige gebruikers** (alleen het tabblad**Uw domeinen):** een verzendende infrastructuur is spoofing meerdere gebruikers, waar sommige vervalste gebruikers zijn toegestaan en anderen niet.</span><span class="sxs-lookup"><span data-stu-id="e39b5-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="e39b5-173">Gebruik het tabblad **Gedetailleerd** om de specifieke adressen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e39b5-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="e39b5-174">Klik onder aan de pagina op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e39b5-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="e39b5-175">PowerShell gebruiken om vervalste afzenders te beheren</span><span class="sxs-lookup"><span data-stu-id="e39b5-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="e39b5-176">Als u toegestane en geblokkeerde afzenders wilt weergeven in spoofinformatie, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e39b5-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="e39b5-177">In dit voorbeeld worden gedetailleerde informatie geretourneerd over alle afzenders die gebruikers in uw domeinen mogen spoofen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="e39b5-178">Zie [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span></span>

<span data-ttu-id="e39b5-179">Voer de volgende stappen uit om toegestane en geblokkeerde afzenders in spoofinformatie te configureren:</span><span class="sxs-lookup"><span data-stu-id="e39b5-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="e39b5-180">Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de cmdlet **Get-PhishFilterPolicy** naar een CSV-bestand te schrijven:</span><span class="sxs-lookup"><span data-stu-id="e39b5-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="e39b5-181">Bewerk het CSV-bestand om de waarden **SpoofedUser** (e-mailadres) en **AllowedToSpoof** (Ja of Nee) toe te voegen of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="e39b5-182">Sla het bestand op, lees het bestand en `$UpdateSpoofedSenders`sla de inhoud op als een variabele met de naam:</span><span class="sxs-lookup"><span data-stu-id="e39b5-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="e39b5-183">Gebruik `$UpdateSpoofedSenders` de variabele om het spoofintelligentiebeleid te configureren:</span><span class="sxs-lookup"><span data-stu-id="e39b5-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="e39b5-184">Zie [Set-PhishFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="e39b5-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="e39b5-185">Het Beveiligingscentrum & compliance gebruiken om spoofinformatie te configureren</span><span class="sxs-lookup"><span data-stu-id="e39b5-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="e39b5-186">De configuratieopties voor spoofinformatie worden beschreven in [spoofinstellingen in antiphishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="e39b5-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="e39b5-187">Uw beschikbare opties zijn afhankelijk van uw abonnement:</span><span class="sxs-lookup"><span data-stu-id="e39b5-187">Your available options depend on your subscription:</span></span>

- <span data-ttu-id="e39b5-188">Zelfstandige EOP-organisaties zonder Exchange Online-postvakken kunnen geen spoofinformatie-instellingen configureren.</span><span class="sxs-lookup"><span data-stu-id="e39b5-188">Standalone EOP organizations without Exchange Online mailboxes can't configure spoof intelligence settings.</span></span>

- <span data-ttu-id="e39b5-189">Microsoft 365-organisaties met Exchange Online-postvakken kunnen spoofinformatie-instellingen configureren in het standaardbeleid (en alleen) antiphishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="e39b5-189">Microsoft 365 organizations with Exchange Online mailboxes can configure spoof intelligence settings in the default (and only) anti-phishing policy.</span></span> <span data-ttu-id="e39b5-190">Zie Het [standaard antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e39b5-190">For instructions, see [Configure the default anti-phishing policy in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="e39b5-191">Microsoft 365-organisaties met ATP kunnen spoofinformatie-instellingen configureren in het standaard ATP-antiphishingbeleid en ook in het aangepaste ATP-antiphishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="e39b5-191">Microsoft 365 organizations with ATP can configure spoof intelligence settings in the default ATP anti-phishing policy, and also in custom ATP anti-phishing policies.</span></span> <span data-ttu-id="e39b5-192">Zie [ATP-antiphishingbeleid configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e39b5-192">For instructions, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e39b5-193">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="e39b5-193">How do you know these procedures worked?</span></span>

<span data-ttu-id="e39b5-194">Gebruik een van de volgende stappen om te controleren of u spoofinformatie hebt geconfigureerd met afzenders die wel en niet mogen spoofen en dat u de instellingen voor spoofinformatie hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="e39b5-194">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="e39b5-195">Ga in het beveiligingscentrum & naar **Beleid bedreigingsbeheer** \> **Policy** \> **Anti-spam** \> uitbreiden **Spoofinformatiebeleid** \> selecteer **Mij afzenders tonen die ik al heb** \> gecontroleerd, selecteer het tabblad **Uw domeinen** of externe **domeinen** en controleer of de waarde Toegestaan om **te spoofen?**</span><span class="sxs-lookup"><span data-stu-id="e39b5-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="e39b5-196">Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die wel en niet mogen spoofen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-196">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="e39b5-197">Voer in PowerShell de volgende opdracht uit om de lijst met alle vervalste afzenders naar een CSV-bestand te exporteren:</span><span class="sxs-lookup"><span data-stu-id="e39b5-197">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="e39b5-198">Ga in Microsoft 365-organisaties met Exchange Online-postvakken een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="e39b5-198">In Microsoft 365 organizations with Exchange Online mailboxes, do either of the following steps:</span></span>

  - <span data-ttu-id="e39b5-199">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span><span class="sxs-lookup"><span data-stu-id="e39b5-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

  - <span data-ttu-id="e39b5-200">Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-200">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- <span data-ttu-id="e39b5-201">Ga in Microsoft 365 ATP-organisaties een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="e39b5-201">In Microsoft 365 ATP organizations, do either of the following steps:</span></span>

  - <span data-ttu-id="e39b5-202">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing** en doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** and do either of the following steps:</span></span>

    - <span data-ttu-id="e39b5-203">Selecteer een beleid in de lijst.</span><span class="sxs-lookup"><span data-stu-id="e39b5-203">Select a policy from the list.</span></span> <span data-ttu-id="e39b5-204">Controleer in de flyout die wordt weergegeven de waarden in de sectie **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="e39b5-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
    - <span data-ttu-id="e39b5-205">Klik **op Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="e39b5-205">Click **Default policy**.</span></span> <span data-ttu-id="e39b5-206">Controleer in de flyout die wordt weergegeven de waarden in de sectie **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="e39b5-206">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

  - <span data-ttu-id="e39b5-207">Vervang in \<Exchange Online\> PowerShell Naam door Office365 AntiPhish Default of de naam van een aangepast ATP-antiphishingbeleid en voer de volgende opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-207">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom ATP anti-phishing policy, and run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="e39b5-208">Andere manieren om spoofing en phishing te beheren</span><span class="sxs-lookup"><span data-stu-id="e39b5-208">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="e39b5-209">Wees ijverig over spoofing en phishing bescherming.</span><span class="sxs-lookup"><span data-stu-id="e39b5-209">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="e39b5-210">Dit zijn gerelateerde manieren om te controleren of afzenders uw domein spoofen en te voorkomen dat ze uw organisatie beschadigen:</span><span class="sxs-lookup"><span data-stu-id="e39b5-210">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="e39b5-211">Controleer het **spoof-e-mailrapport**.</span><span class="sxs-lookup"><span data-stu-id="e39b5-211">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="e39b5-212">U dit rapport vaak gebruiken om vervalste afzenders te bekijken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="e39b5-212">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="e39b5-213">Zie Rapport [Spoofdetecties](view-email-security-reports.md#spoof-detections-report)voor informatie .</span><span class="sxs-lookup"><span data-stu-id="e39b5-213">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="e39b5-214">Bekijk de SPF-configuratie (Sender Policy Framework).</span><span class="sxs-lookup"><span data-stu-id="e39b5-214">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="e39b5-215">Zie [SPF instellen in Microsoft 365 om spoofing te voorkomen voor](set-up-spf-in-office-365-to-help-prevent-spoofing.md)een snelle introductie tot SPF en om deze snel te configureren.</span><span class="sxs-lookup"><span data-stu-id="e39b5-215">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="e39b5-216">Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="e39b5-216">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="e39b5-217">Controleer de configuratie van uw DomainKeys Identified Mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="e39b5-217">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="e39b5-218">U moet DKIM gebruiken naast SPF en DMARC om te voorkomen dat aanvallers berichten verzenden die eruit zien alsof ze uit uw domein komen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-218">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="e39b5-219">Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="e39b5-219">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="e39b5-220">Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Office 365 is verzonden, te valideren](use-dkim-to-validate-outbound-email.md)voor informatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-220">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="e39b5-221">Controleer uw domeingebaseerde berichtverificatie- en rapportageconfiguratie (DMARC).</span><span class="sxs-lookup"><span data-stu-id="e39b5-221">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="e39b5-222">De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email.</span><span class="sxs-lookup"><span data-stu-id="e39b5-222">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="e39b5-223">DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen.</span><span class="sxs-lookup"><span data-stu-id="e39b5-223">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="e39b5-224">Zie [DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e39b5-224">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>