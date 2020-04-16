---
title: Zero-hour auto purge (ZAP) - met terugwerkende kracht bescherming tegen spam, malware en phishing.
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
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-hour auto purge (ZAP) is een functie voor e-mailbeveiliging in Office 365 die spam-, malware- of phishingberichten detecteert die al bij Exchange Online zijn bezorgd. Hoe ZAP dit doet, hangt af van het type schadelijke inhoud dat wordt gedetecteerd.
ms.openlocfilehash: 44bdab5d37863bc543d953a89ac3129b3530437d
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516771"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-office-365"></a><span data-ttu-id="d5ce3-104">Zero-hour auto purge (ZAP) - bescherming tegen spam en malware in Office 365</span><span class="sxs-lookup"><span data-stu-id="d5ce3-104">Zero-hour auto purge (ZAP) - protection against spam and malware in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="d5ce3-105">Overzicht</span><span class="sxs-lookup"><span data-stu-id="d5ce3-105">Overview</span></span>

<span data-ttu-id="d5ce3-106">Zero-hour auto purge (ZAP) is een functie voor e-mailbeveiliging in Office 365 die met terugwerkende kracht schadelijke phishing-, spam- of malwareberichten detecteert en neutraliseert die al zijn afgeleverd bij Postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-106">Zero-hour auto purge (ZAP) is an email protection feature in Office 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="d5ce3-107">ZAP is beschikbaar met de standaard Exchange Online Protection (EOP) die is inbegrepen bij elk Office 365-abonnement dat Exchange Online-postvakken bevat.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-107">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="d5ce3-108">ZAP werkt niet in zelfstandige EOP-omgevingen die on-premises Exchange-postvakken beschermen.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-108">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="d5ce3-109">Hoe ZAP werkt</span><span class="sxs-lookup"><span data-stu-id="d5ce3-109">How ZAP works</span></span>

<span data-ttu-id="d5ce3-110">Office 365 werkt dagelijks spam- en malwarehandtekeningen in realtime bij.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-110">Office 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="d5ce3-111">Gebruikers kunnen echter nog steeds schadelijke berichten ontvangen om verschillende redenen, waaronder als inhoud wordt bewapend nadat ze aan gebruikers zijn geleverd.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-111">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="d5ce3-112">ZAP lost dit probleem op door voortdurend updates van de handtekeningen van Office 365-spam en malware te controleren.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-112">ZAP addresses this issue by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="d5ce3-113">ZAP kan berichten vinden en verwijderen die zich al in het postvak van een gebruiker bevinden.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-113">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="d5ce3-114">De ZAP-actie is naadloos voor de gebruiker; ze worden niet op de hoogte gesteld als een bericht wordt gedetecteerd en verplaatst.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-114">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="d5ce3-115">[Lijsten met veilige afzenders,](create-safe-sender-lists-in-office-365.md)regels voor e-mailstromen (ook wel transportregels genoemd), Postvak IN-regels of extra filters hebben voorrang op ZAP.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-115">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="d5ce3-116">Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="d5ce3-116">Malware ZAP</span></span>

<span data-ttu-id="d5ce3-117">Voor **lees- of ongelezen berichten** die malware blijken te bevatten na levering, quarantainet ZAP het bericht dat de malwarebijlage bevat.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="d5ce3-118">Alleen beheerders kunnen malwareberichten vanuit quarantaine bekijken en beheren.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="d5ce3-119">Malware ZAP is standaard ingeschakeld in anti-malwarebeleid.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="d5ce3-120">Zie [Beleid voor antimalware configureren in Office 365](configure-anti-malware-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-120">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="d5ce3-121">Phish ZAP</span><span class="sxs-lookup"><span data-stu-id="d5ce3-121">Phish ZAP</span></span>

<span data-ttu-id="d5ce3-122">Voor **gelezen of ongelezen berichten** die na levering als phish worden geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor een **phishing-e-mailfilteringvonnis** in het toepasselijke antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="d5ce3-123">De beschikbare filtering verdict acties voor phish en hun mogelijke ZAP resultaten worden beschreven in de volgende lijst:</span><span class="sxs-lookup"><span data-stu-id="d5ce3-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="d5ce3-124">**X-Header**, **Prepend onderwerpregel toevoegen met tekst:** ZAP onderneemt geen actie op het bericht.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="d5ce3-125">**Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="d5ce3-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="d5ce3-126">Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="d5ce3-127">**Bericht omleiden naar e-mailadres**, **Bericht verwijderen**, **Quarantainebericht:** ZAP zet het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="d5ce3-128">Alleen beheerders kunnen in quarantaine geplaatste berichten in quarantaine bekijken en beheren.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-128">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="d5ce3-129">Standaard is phish ZAP ingeschakeld in antispambeleid en de standaardactie voor het **phishing-e-mailfiltervonnis** is **Quarantainebericht**, wat betekent dat phish ZAP het bericht standaard in quarantaine zet.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-129">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="d5ce3-130">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van spamfilteruitspraken.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-130">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="d5ce3-131">Spam ZAP</span><span class="sxs-lookup"><span data-stu-id="d5ce3-131">Spam ZAP</span></span>

<span data-ttu-id="d5ce3-132">Voor **ongelezen berichten** die na levering als spam worden geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor **het** spamfiltervonnis in het toepasselijke antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-132">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="d5ce3-133">De beschikbare filtering verdict acties voor spam en de mogelijke ZAP resultaten worden beschreven in de volgende lijst:</span><span class="sxs-lookup"><span data-stu-id="d5ce3-133">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="d5ce3-134">**X-Header**, **Prepend onderwerpregel toevoegen met tekst:** ZAP onderneemt geen actie op het bericht.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-134">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="d5ce3-135">**Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="d5ce3-135">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="d5ce3-136">Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-136">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="d5ce3-137">**Bericht omleiden naar e-mailadres**, **Bericht verwijderen**, **Quarantainebericht:** ZAP zet het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-137">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="d5ce3-138">Eindgebruikers kunnen hun eigen spamberichten in quarantaine bekijken en beheren.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-138">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="d5ce3-139">Standaard is spam ZAP ingeschakeld in antispambeleid en de standaardactie voor **het** spamfiltervonnis is Bericht verplaatsen naar **ongewenste e-mailmap,** wat betekent dat spam ZAP **standaard ongelezen** berichten naar de map Ongewenste e-mail verplaatst.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-139">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="d5ce3-140">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van spamfilteruitspraken.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-140">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="d5ce3-141">ZAP-overwegingen voor Office 365 Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="d5ce3-141">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="d5ce3-142">ZAP zal geen bericht in quarantaine plaatsen dat aan het scannen van [Dynamic Delivery](dynamic-delivery-and-previewing.md) is, of waar malwarefiltering de bijlage al heeft vervangen door het bestand Malware **Alert Text.txt.**</span><span class="sxs-lookup"><span data-stu-id="d5ce3-142">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="d5ce3-143">Als een phish- of spamsignaal wordt ontvangen voor dit soort berichten en het filtervonnis in het antispambeleid is ingesteld om actie te ondernemen op het bericht (Verplaatsen naar ongewenstee items, omleiding, quarantaine, quarantaine) dan zal ZAP standaard een actie 'Verplaatsen naar ongewenste e-mail' uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-143">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="d5ce3-144">Hoe u zien of ZAP uw bericht heeft verplaatst</span><span class="sxs-lookup"><span data-stu-id="d5ce3-144">How to see if ZAP moved your message</span></span>

<span data-ttu-id="d5ce3-145">Als u wilt bepalen of ZAP uw bericht heeft verplaatst, u het [rapport Status bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report) of [Threat Explorer (en realtime detecties)](threat-explorer.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-145">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="d5ce3-146">Als systeemactie is ZAP niet aangemeld bij de controlelogboeken van het Exchange-postvak.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-146">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="d5ce3-147">VEELgestelde VRAGEN OVER ZAP</span><span class="sxs-lookup"><span data-stu-id="d5ce3-147">ZAP FAQ</span></span>

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="d5ce3-148">V: Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?</span><span class="sxs-lookup"><span data-stu-id="d5ce3-148">Q: What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="d5ce3-149">A: U moet het normale rapportageproces volgen voor [false positives.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d5ce3-149">A: You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="d5ce3-150">De enige reden waarom het bericht zou worden verplaatst van de Inbox naar de map Ongewenste e-mail zou zijn omdat de service heeft vastgesteld dat het bericht was spam of kwaadaardig.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-150">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="q-what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="d5ce3-151">V: Wat als ik de quarantaine van Office 365 gebruik in plaats van de map Ongewenste e-mail?</span><span class="sxs-lookup"><span data-stu-id="d5ce3-151">Q: What if I use the Office 365 quarantine instead of the Junk Mail folder?</span></span>

<span data-ttu-id="d5ce3-152">A: ZAP onderneemt actie op basis van een bericht op basis van de configuratie van uw antispambeleid zoals eerder in dit onderwerp is beschreven.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-152">A: ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="d5ce3-153">V: Wat als ik e-mailstroomregels of toegestane/geblokkeerde afzenderlijsten gebruik?</span><span class="sxs-lookup"><span data-stu-id="d5ce3-153">Q: What if I'm using mail flow rules or allowed/blocked sender lists?</span></span>

<span data-ttu-id="d5ce3-154">A: Regels voor e-mailstroom of blokkeren en organisatorische instellingen toestaan, hebben voorrang.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-154">A: Mail flow rules or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="d5ce3-155">Deze berichten zijn uitgesloten van ZAP.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-155">These messages are excluded from ZAP.</span></span>

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="d5ce3-156">V: Wat gebeurt er als een bericht naar een andere map wordt verplaatst (bijvoorbeeld regels in postvak IN)?</span><span class="sxs-lookup"><span data-stu-id="d5ce3-156">Q: What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="d5ce3-157">A: ZAP werkt nog steeds zolang het bericht niet is verwijderd, of zolang hetzelfde of sterker, actie nog niet is toegepast.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-157">A:  ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="d5ce3-158">Als het phish-beleid bijvoorbeeld is ingesteld op quarantaine en de gebruiker of beheerder de e-mail al heeft gejunked, wordt er in quarantaine actie ondernomen om het bestand in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="q-does-zap-change-the-message-header"></a><span data-ttu-id="d5ce3-159">V: Wijzigt ZAP de berichtkop?</span><span class="sxs-lookup"><span data-stu-id="d5ce3-159">Q: Does ZAP change the message header?</span></span>

<span data-ttu-id="d5ce3-160">A: Een ZAP-actie brengt geen wijzigingen aan in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-160">A: A ZAP action does not make any changes to the message header.</span></span>

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="d5ce3-161">V: Hoe beïnvloedt ZAP mailboxen in de wacht?</span><span class="sxs-lookup"><span data-stu-id="d5ce3-161">Q: How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="d5ce3-162">A: ZAP zal geen berichten van postvakken in de wacht plaatsen.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-162">A: ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="d5ce3-163">ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor een spam- of phishingvonnis in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-163">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="d5ce3-164">Zie [In-Place Hold en Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)voor meer informatie over blokkeringen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d5ce3-164">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
