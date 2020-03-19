---
title: Regels voor e-mailstroom gebruiken om bulke-mailfiltering in Exchange Online Protection te configureren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze regels voor e-mailstromen kunnen gebruiken in Exchange Online Protection voor bulke-mailfiltering.
ms.openlocfilehash: 81b0f4cc58d712c3a1c1e09dab02d1c6f56cb69d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809173"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="7451c-103">Regels voor e-mailstroom gebruiken om bulke-mailfiltering in Exchange Online Protection te configureren</span><span class="sxs-lookup"><span data-stu-id="7451c-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="7451c-104">U bedrijfsbrede inhoudsfilters instellen voor spam en bulke-mail met behulp van het standaardbeleid voor spaminhoud.</span><span class="sxs-lookup"><span data-stu-id="7451c-104">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies.</span></span> <span data-ttu-id="7451c-105">Bekijk [Het beleid voor spamfilters](configure-your-spam-filter-policies.md) configureren en het beleid voor [inhoudsfilter instellen](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) over het instellen van het beleid voor inhoudsfilter.</span><span class="sxs-lookup"><span data-stu-id="7451c-105">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) on how to set the content filter policies.</span></span>

<span data-ttu-id="7451c-106">Als u meer opties wilt om bulkberichten te filteren, u regels voor e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of -zinnen die vaak in bulke-mails worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="7451c-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="7451c-107">Elk bericht met deze kenmerken wordt gemarkeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="7451c-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="7451c-108">Het gebruik van deze regels kan helpen de hoeveelheid ongewenste bulke-mail die uw organisatie ontvangt te verminderen.</span><span class="sxs-lookup"><span data-stu-id="7451c-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7451c-109">Voordat u de regels voor de e-mailstroom maakt die dit onderwerp hebben gedocumenteerd, [Bulk Complaint Level values](bulk-complaint-level-values.md)raden we u aan eerst te lezen [Wat is het verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="7451c-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br>
> <span data-ttu-id="7451c-110">De volgende procedures markeren een bericht als spam voor uw hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="7451c-110">The following procedures mark a message as spam for your entire organization.</span></span> <span data-ttu-id="7451c-111">U echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke ontvangers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7451c-111">However, you can add another condition to apply these rules only to specific recipients in your organization.</span></span> <span data-ttu-id="7451c-112">Op deze manier kunnen de agressieve instellingen voor bulke-mailfiltering van toepassing zijn op een paar gebruikers die zeer gericht zijn, terwijl de rest van uw gebruikers (die meestal de bulke-mail krijgen waarvoor ze zich hebben aangemeld) niet worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="7451c-112">This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="7451c-113">Een e-mailstroomregel maken om bulke-mailberichten te filteren op basis van tekstpatronen</span><span class="sxs-lookup"><span data-stu-id="7451c-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="7451c-114">Ga in het Exchange-beheercentrum (EAC) naar **Regels voor de mailstroom** \> **.**</span><span class="sxs-lookup"><span data-stu-id="7451c-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="7451c-115">Klik **Add** ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram Toevoegen toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="7451c-115">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="7451c-116">Geef een naam voor de regel op.</span><span class="sxs-lookup"><span data-stu-id="7451c-116">Specify a name for the rule.</span></span>

4. <span data-ttu-id="7451c-117">Klik op **Meer** ![](../../media/ITPro-EAC-MoreOptionsIcon.png)opties Pictogram Meer opties .</span><span class="sxs-lookup"><span data-stu-id="7451c-117">Click **More options** ![More options icon](../../media/ITPro-EAC-MoreOptionsIcon.png).</span></span> <span data-ttu-id="7451c-118">Selecteer onder **Toepassen van deze regel als**u Het onderwerp of de **hoofdtekst** \> selecteert **die overeenkomt met deze tekstpatronen**.</span><span class="sxs-lookup"><span data-stu-id="7451c-118">Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>

5. <span data-ttu-id="7451c-119">Voeg in het dialoogvenster **Woorden of zinnen** opgeven de volgende reguliere expressies toe die vaak worden gevonden in bulke-mails, één voor één, en klik op **OK** wanneer u klaar bent:</span><span class="sxs-lookup"><span data-stu-id="7451c-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **OK** when you're done:</span></span>

   - `If you are unable to view the content of this email\, please`

   - `\>(safe )?unsubscribe( here)?\</a\>`

   - `If you do not wish to receive further communications like this\, please`

   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

   - `To stop receiving these+emails\:http\://`

   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

   - `no longer (wish )?(to )?(be sent|receive) w+ email`

   - `If you are unable to view the content of this email\, please click here`

   - `To ensure you receive (your daily deals|our e-?mails)\, add`

   - `If you no longer wish to receive these emails`

   - `to change your (subscription preferences|preferences or unsubscribe)`

   - `click (here to|the) unsubscribe`

   <span data-ttu-id="7451c-120">De bovenstaande lijst is niet een uitputtende set van regelmatige uitdrukkingen gevonden in bulk e-mails; meer kan worden toegevoegd of verwijderd als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="7451c-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="7451c-121">Het is echter een goed uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="7451c-121">However, it's a good starting point.</span></span>

   <span data-ttu-id="7451c-122">De zoekopdracht naar woorden of tekstpatronen in het onderwerp of andere kopvelden in het bericht vindt plaats *nadat* het bericht is gedecodeerd uit de mime-methode voor het coderen van inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden.</span><span class="sxs-lookup"><span data-stu-id="7451c-122">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="7451c-123">U geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de onbewerkte (doorgaans Base64) gecodeerde waarden van het onderwerp of andere kopvelden in berichten.</span><span class="sxs-lookup"><span data-stu-id="7451c-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

6. <span data-ttu-id="7451c-124">Selecteer onder **Ga als volgt**de optie De \> eigenschappen van het bericht **wijzigen** **en stel het betrouwbaarheidsniveau voor spam (SCL)** in .</span><span class="sxs-lookup"><span data-stu-id="7451c-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="7451c-125">Stel in het dialoogvenster **SCL** op **5,** **6**of **9**op op opgeven en klik op **ok**.</span><span class="sxs-lookup"><span data-stu-id="7451c-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="7451c-126">Als u de SCL instelt op 5 of 6, neemt de **actie Spam in** beslag, terwijl het instellen van de SCL op 9 de **spamactie met veel vertrouwen** neemt, zoals geconfigureerd in het beleid voor inhoudsfilter.</span><span class="sxs-lookup"><span data-stu-id="7451c-126">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="7451c-127">De service voert de actieset uit in het beleid voor inhoudsfilter.</span><span class="sxs-lookup"><span data-stu-id="7451c-127">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="7451c-128">De standaardactie is om het bericht te leveren aan de map Ongewenste e-mail van de geadresseerden, maar verschillende acties kunnen worden geconfigureerd zoals beschreven in [Het beleid voor spamfilters](configure-your-spam-filter-policies.md)configureren .</span><span class="sxs-lookup"><span data-stu-id="7451c-128">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="7451c-129">Als uw geconfigureerde actie is om het bericht in quarantaine te plaatsen in plaats van het te verzenden naar de map Ongewenste e-mail van de geadresseerden, wordt het bericht verzonden naar de beheerder quarantaine als een e-mailstroomregel overeenkomen, en het zal niet beschikbaar zijn in de quarantaine van de eindgebruiker of via de eindgebruiker spammeldingen.</span><span class="sxs-lookup"><span data-stu-id="7451c-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="7451c-130">Zie [Vertrouwensniveaus](spam-confidence-levels.md)voor spam voor meer informatie over SCL-waarden in de service.</span><span class="sxs-lookup"><span data-stu-id="7451c-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="7451c-131">Sla de regel op.</span><span class="sxs-lookup"><span data-stu-id="7451c-131">Save the rule.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="7451c-132">Een e-mailstroomregel maken om bulke-mailberichten te filteren op basis van zinnen</span><span class="sxs-lookup"><span data-stu-id="7451c-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="7451c-133">Ga in de EAC naar **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="7451c-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="7451c-134">Klik **Add** ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram Toevoegen toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="7451c-134">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="7451c-135">Geef een naam voor de regel op.</span><span class="sxs-lookup"><span data-stu-id="7451c-135">Specify a name for the rule.</span></span>

4. <span data-ttu-id="7451c-136">Klik **op Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="7451c-136">Click **More options**.</span></span> <span data-ttu-id="7451c-137">Selecteer onder **Toepassen van deze regel als**u Het onderwerp of de **instantie** \> **of het lichaam een van deze woorden bevat**.</span><span class="sxs-lookup"><span data-stu-id="7451c-137">Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>

5. <span data-ttu-id="7451c-138">Voeg in het dialoogvenster **Woorden of zinnen** op te geven de volgende zinnen die vaak worden gevonden in bulke-mails, één voor één, toe en klik op **ok** wanneer u klaar bent:</span><span class="sxs-lookup"><span data-stu-id="7451c-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span>

   - `to change your preferences or unsubscribe`

   - `Modify email preferences or unsubscribe`

   - `This is a promotional email`

   - `You are receiving this email because you requested a subscription`

   - `click here to unsubscribe`

   - `You have received this email because you are subscribed`

   - `If you no longer wish to receive our email newsletter`

   - `to unsubscribe from this newsletter`

   - `If you have trouble viewing this email`

   - `This is an advertisement`

   - `you would like to unsubscribe or change your`

   - `view this email as a webpage`

   - `You are receiving this email because you are subscribed`

   <span data-ttu-id="7451c-139">Deze lijst is niet een uitputtende set van zinnen gevonden in bulk e-mails; meer kan worden toegevoegd of verwijderd als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="7451c-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="7451c-140">Het is echter een goed uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="7451c-140">However, it's a good starting point.</span></span>

6. <span data-ttu-id="7451c-141">Selecteer onder **Ga als volgt**de optie De \> eigenschappen van het bericht **wijzigen** **en stel het betrouwbaarheidsniveau voor spam (SCL)** in .</span><span class="sxs-lookup"><span data-stu-id="7451c-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="7451c-142">Stel in het dialoogvenster **SCL** op **5,** **6**of **9**op op opgeven en klik op **ok**.</span><span class="sxs-lookup"><span data-stu-id="7451c-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="7451c-143">Als u de SCL instelt op 5 of 6, neemt de **actie Spam in** beslag, terwijl het instellen van de SCL op 9 de **spamactie met veel vertrouwen** neemt, zoals geconfigureerd in het beleid voor inhoudsfilter.</span><span class="sxs-lookup"><span data-stu-id="7451c-143">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="7451c-144">De service voert de actieset uit in het beleid voor inhoudsfilter.</span><span class="sxs-lookup"><span data-stu-id="7451c-144">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="7451c-145">De standaardactie is om het bericht te leveren aan de map Ongewenste e-mail van de geadresseerden, maar verschillende acties kunnen worden geconfigureerd zoals beschreven in [Het beleid voor spamfilters](configure-your-spam-filter-policies.md)configureren .</span><span class="sxs-lookup"><span data-stu-id="7451c-145">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="7451c-146">Als uw geconfigureerde actie is om het bericht in quarantaine te plaatsen in plaats van het te verzenden naar de map Ongewenste e-mail van de geadresseerden, wordt het bericht verzonden naar de beheerder quarantaine als een e-mailstroomregel overeenkomen, en het zal niet beschikbaar zijn in de quarantaine van de eindgebruiker of via de eindgebruiker spammeldingen.</span><span class="sxs-lookup"><span data-stu-id="7451c-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="7451c-147">Zie [Vertrouwensniveaus](spam-confidence-levels.md)voor spam voor meer informatie over SCL-waarden in de service.</span><span class="sxs-lookup"><span data-stu-id="7451c-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="7451c-148">Sla de regel op.</span><span class="sxs-lookup"><span data-stu-id="7451c-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="7451c-149">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="7451c-149">For more information</span></span>

[<span data-ttu-id="7451c-150">Wat is het verschil tussen ongewenste e-mail en bulke-mail?</span><span class="sxs-lookup"><span data-stu-id="7451c-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="7451c-151">Waarden op bulkklachtenniveau</span><span class="sxs-lookup"><span data-stu-id="7451c-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="7451c-152">Uw spamfilterbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="7451c-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="7451c-153">Geavanceerde opties voor spamfilter</span><span class="sxs-lookup"><span data-stu-id="7451c-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
