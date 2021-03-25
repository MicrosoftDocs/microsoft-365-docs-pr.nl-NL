---
title: Regels voor e-mailstroom gebruiken om bulk-e-mail te filteren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (transportregels) kunnen gebruiken om bulkmail (grijze e-mail) te identificeren en te filteren in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204444"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="e6715-103">E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="e6715-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6715-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e6715-104">**Applies to**</span></span>
- [<span data-ttu-id="e6715-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e6715-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e6715-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e6715-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e6715-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6715-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e6715-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam en bulkmail (ook wel grijze e-mail genoemd).</span><span class="sxs-lookup"><span data-stu-id="e6715-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="e6715-109">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6715-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e6715-110">Als u meer opties wilt om bulkmail te filteren, kunt u regels voor de e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of woordgroepen die vaak worden gevonden in bulkmail en deze berichten markeren als spam.</span><span class="sxs-lookup"><span data-stu-id="e6715-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="e6715-111">Zie Wat is het [](what-s-the-difference-between-junk-email-and-bulk-email.md) verschil tussen ongewenste e-mail en bulk-e-mail? en Bulk [complaint level (BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over bulkmail.</span><span class="sxs-lookup"><span data-stu-id="e6715-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="e6715-112">In dit onderwerp wordt uitgelegd hoe u deze regels voor de e-mailstroom maakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="e6715-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6715-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e6715-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6715-114">U moet machtigingen krijgen toegewezen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e6715-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="e6715-115">U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e6715-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="e6715-116">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="e6715-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="e6715-117">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6715-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="e6715-118">Machtigingen in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="e6715-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="e6715-119">De lijst met leden in rollengroepen wijzigen met het EAC</span><span class="sxs-lookup"><span data-stu-id="e6715-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="e6715-120">Zie [Exchange-beheercentrum in Exchange Online](/Exchange/exchange-admin-center)om het EAC in Exchange Online te openen.</span><span class="sxs-lookup"><span data-stu-id="e6715-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="e6715-121">Zie [Exchange-beheercentrum in](exchange-admin-center-in-exchange-online-protection-eop.md)zelfstandige EOP om de EAC in zelfstandige EOP te openen.</span><span class="sxs-lookup"><span data-stu-id="e6715-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e6715-122">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6715-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e6715-123">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6715-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e6715-124">Zie de volgende onderwerpen voor meer informatie over e-mailstroomregels in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="e6715-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="e6715-125">Regels voor e-mailstroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6715-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="e6715-126">Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6715-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="e6715-127">Acties voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6715-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="e6715-128">De lijst met woorden en tekstpatronen die worden gebruikt om bulkmail in de voorbeelden te identificeren, is niet volledig. u kunt indien nodig vermeldingen toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6715-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="e6715-129">Ze zijn echter een goed beginpunt.</span><span class="sxs-lookup"><span data-stu-id="e6715-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="e6715-130">Het zoeken naar woorden of tekstpatronen in het onderwerp  of andere koptekstvelden in het bericht vindt plaats nadat het bericht is gedecodeerd met de MIME-methode voor inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden.</span><span class="sxs-lookup"><span data-stu-id="e6715-130">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="e6715-131">U kunt geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de onbewerkte (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.</span><span class="sxs-lookup"><span data-stu-id="e6715-131">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="e6715-132">In de volgende procedures wordt een bulkbericht gemarkeerd als spam voor uw hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="e6715-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="e6715-133">U kunt echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke geadresseerden, zodat u agressieve filtering kunt gebruiken voor een paar zeer gerichte gebruikers, terwijl de rest van uw gebruikers (die meestal de bulk-e-mail ontvangen waar ze zich voor hebben aangemeld) geen invloed hebben.</span><span class="sxs-lookup"><span data-stu-id="e6715-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="e6715-134">EAC gebruiken om regels voor e-mailstroom te maken die bulk-e-mail filteren</span><span class="sxs-lookup"><span data-stu-id="e6715-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="e6715-135">Ga in het EAC naar **E-mailstroomregels.** \> </span><span class="sxs-lookup"><span data-stu-id="e6715-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="e6715-136">Klik **op Pictogram** Toevoegen toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="e6715-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="e6715-137">Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="e6715-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e6715-138">**Naam:** Voer een unieke, beschrijvende naam in voor de regel.</span><span class="sxs-lookup"><span data-stu-id="e6715-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="e6715-139">Klik **op Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="e6715-139">Click **More Options**.</span></span>

   - <span data-ttu-id="e6715-140">**Pas deze regel toe als**: Configureer een van de volgende instellingen om te zoeken naar inhoud in berichten met gewone expressies (RegEx) of woorden of woordgroepen:</span><span class="sxs-lookup"><span data-stu-id="e6715-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="e6715-141">**Het onderwerp of de body** \> **onderwerp** of de teksttekst komt  overeen met deze tekstpatronen: Voer in het dialoogvenster  Woorden of woordgroepen opgeven dat wordt weergegeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="e6715-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="e6715-142">Als u een item wilt bewerken, selecteert u deze en klikt **u** op ![ Pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="e6715-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="e6715-143">Als u een item wilt verwijderen, selecteert u deze en klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6715-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="e6715-144">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6715-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="e6715-145">**Het onderwerp of de body** \> **onderwerp** of de tekst bevat een  van deze woorden: Voer in het dialoogvenster Woorden  of woordgroepen opgeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="e6715-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="e6715-146">Als u een item wilt bewerken, selecteert u deze en klikt **u** op ![ Pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="e6715-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="e6715-147">Als u een item wilt verwijderen, selecteert u deze en klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e6715-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="e6715-148">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="e6715-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="e6715-149">**Ga als volgt te** werk: Selecteer **De eigenschappen van het bericht wijzigen** om \> **het betrouwbaarheidsniveau voor spam (SCL) in te stellen.**</span><span class="sxs-lookup"><span data-stu-id="e6715-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="e6715-150">Configureer een van de volgende instellingen in het dialoogvenster **SCL** opgeven dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e6715-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="e6715-151">Als u berichten wilt markeren **als Spam,** selecteert u **6**.</span><span class="sxs-lookup"><span data-stu-id="e6715-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="e6715-152">De actie die u hebt  geconfigureerd voor spamfilters in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="e6715-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="e6715-153">Als u berichten wilt markeren als **spam met hoog vertrouwen,** **selecteert u 9**.</span><span class="sxs-lookup"><span data-stu-id="e6715-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="e6715-154">De actie die u hebt  geconfigureerd voor het filteren van spam met hoge betrouwbaarheid in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**</span><span class="sxs-lookup"><span data-stu-id="e6715-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="e6715-155">Zie Betrouwbaarheidsniveau [spam (SCL) in EOP voor meer informatie over SCL-waarden.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="e6715-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="e6715-156">Wanneer u klaar bent, klikt u op **Opslaan**</span><span class="sxs-lookup"><span data-stu-id="e6715-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="e6715-157">PowerShell gebruiken om regels voor e-mailstroom te maken die bulk-e-mail filteren</span><span class="sxs-lookup"><span data-stu-id="e6715-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="e6715-158">Gebruik de volgende syntaxis om een of beide regels voor de e-mailstroom (gewone expressies versus woorden) te maken:</span><span class="sxs-lookup"><span data-stu-id="e6715-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="e6715-159">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam Bulk-e-mailfiltering - RegEx, waarin dezelfde lijst met reguliere expressies uit eerder in het onderwerp wordt gebruikt om berichten in te stellen als **Spam.**</span><span class="sxs-lookup"><span data-stu-id="e6715-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="e6715-160">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulksgewijs filteren van e-mail - Woorden' waarin dezelfde lijst met woorden uit eerder in het onderwerp wordt gebruikt om berichten in te stellen als spam **met hoog vertrouwen.**</span><span class="sxs-lookup"><span data-stu-id="e6715-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="e6715-161">Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6715-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e6715-162">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="e6715-162">How do you know this worked?</span></span>

<span data-ttu-id="e6715-163">Als u wilt controleren of u regels voor e-mailstroom hebt geconfigureerd om bulk-e-mail te filteren, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="e6715-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="e6715-164">Ga in het EAC naar **E-mailstroomregels** en selecteer de regel op Pictogram Bewerken \>  \> bewerken en \> controleer de  ![ ](../../media/ITPro-EAC-EditIcon.png) instellingen.</span><span class="sxs-lookup"><span data-stu-id="e6715-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="e6715-165">Vervang in PowerShell door de naam van de regel en voer de volgende \<Rule Name\> opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="e6715-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="e6715-166">Verzend vanuit een extern account een testberichten naar een getroffen geadresseerde die een van de zinnen of tekstpatronen bevat en controleer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="e6715-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>