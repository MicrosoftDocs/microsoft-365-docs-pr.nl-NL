---
title: Regels voor e-mailstromen gebruiken om bulke-mail te filteren in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Beheerders kunnen leren hoe u regels voor e-mailstroom gebruiken in Exchange Online Protection voor het filteren van bulke-mail.
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895045"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="685a9-103">Regels voor e-mailstromen gebruiken om bulke-mail te filteren in Office 365</span><span class="sxs-lookup"><span data-stu-id="685a9-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="685a9-104">Als u een Office 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection-klant (EOP) zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook wel beleid voor spamfilters of inhoudsfilterbeleid genoemd) om te scannen binnenkomende berichten voor spam en bulkmail (ook wel grijze e-mail genoemd).</span><span class="sxs-lookup"><span data-stu-id="685a9-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="685a9-105">Zie [Beleid voor antispam configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="685a9-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="685a9-106">Als u meer opties wilt filteren voor bulkmail, u regels voor e-mailstromen (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of zinnen die vaak in bulkmail worden gevonden en deze berichten markeren als spam.</span><span class="sxs-lookup"><span data-stu-id="685a9-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="685a9-107">Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) en [Bulk klachtenniveau (BCL) in Office 365](bulk-complaint-level-values.md)voor meer informatie over bulkmail.</span><span class="sxs-lookup"><span data-stu-id="685a9-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="685a9-108">In dit onderwerp wordt uitgelegd hoe deze regels voor e-mailstroom worden gemaakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Office 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).</span><span class="sxs-lookup"><span data-stu-id="685a9-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="685a9-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="685a9-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="685a9-110">U moet machtigingen in Exchange Online krijgen toegewezen voordat u deze procedures uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="685a9-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="685a9-111">U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.**</span><span class="sxs-lookup"><span data-stu-id="685a9-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="685a9-112">Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="685a9-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="685a9-113">Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)als u de EAC in Exchange Online wilt openen.</span><span class="sxs-lookup"><span data-stu-id="685a9-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="685a9-114">Zie Verbinding maken met Exchange Online PowerShell als u verbinding wilt maken met Exchange Online [PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="685a9-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="685a9-115">Zie Verbinding maken met Exchange Online Protection PowerShell als u verbinding wilt maken met zelfstandige Exchange Online Protection [PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="685a9-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="685a9-116">Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="685a9-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="685a9-117">Regels voor e-mailstroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="685a9-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="685a9-118">Voorwaarden en uitzonderingen voor e-mailstroomregels (predicaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="685a9-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="685a9-119">Acties voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="685a9-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="685a9-120">De lijst met woorden en tekstpatronen die worden gebruikt om bulkpost in de voorbeelden te identificeren, is niet volledig; u items indien nodig toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="685a9-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="685a9-121">Ze zijn echter een goed uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="685a9-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="685a9-122">Het zoeken naar woorden of tekstpatronen in de onderwerp- of andere koptekstvelden in het bericht vindt plaats *nadat* het bericht is gedecodeerd vanuit de MIME-inhoudsoverdrachtcoderingsmethode die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden.</span><span class="sxs-lookup"><span data-stu-id="685a9-122">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="685a9-123">U geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de ruwe (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.</span><span class="sxs-lookup"><span data-stu-id="685a9-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="685a9-124">De volgende procedures markeren een bulkbericht als spam voor uw hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="685a9-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="685a9-125">U echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke ontvangers, zodat u agressieve filtering gebruiken op een paar, zeer gerichte gebruikers, terwijl de rest van uw gebruikers (die meestal de bulke-mail krijgen waarvoor ze zich hebben aangemeld) geen invloed hebben.</span><span class="sxs-lookup"><span data-stu-id="685a9-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="685a9-126">De EAC gebruiken om regels voor e-mailstromen te maken die bulke-mail filteren</span><span class="sxs-lookup"><span data-stu-id="685a9-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="685a9-127">Ga in de EAC naar **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="685a9-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="685a9-128">Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="685a9-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="685a9-129">Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="685a9-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="685a9-130">**Naam:** Voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="685a9-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="685a9-131">Klik **op Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="685a9-131">Click **More Options**.</span></span>

   - <span data-ttu-id="685a9-132">**Pas deze regel toe als:** Een van de volgende instellingen configureren om inhoud in berichten te zoeken met behulp van reguliere expressies (RegEx) of woorden of zinnen:</span><span class="sxs-lookup"><span data-stu-id="685a9-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="685a9-133">**Het onderwerp of het onderwerp** \> van het **hoofd of de hoofdtekst komt overeen met deze tekstpatronen:** Voer in het dialoogvenster **Woorden of zinnen opgeven** dat wordt weergegeven een van de volgende waarden in, **klik** ![op Pictogram](../../media/ITPro-EAC-AddIcon.png)toevoegen en herhaal zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="685a9-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

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

      <span data-ttu-id="685a9-134">Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken .</span><span class="sxs-lookup"><span data-stu-id="685a9-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="685a9-135">Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="685a9-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="685a9-136">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="685a9-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="685a9-137">**Het onderwerp of het onderwerp** \> **of de hoofdtekst bevat een van deze woorden:** In het dialoogvenster Woorden](../../media/ITPro-EAC-AddIcon.png)of zinnen **opgeven** dat wordt weergegeven, voert u een van de volgende waarden in, **klikt** ![u op Pictogram toevoegen en herhaal tumoet zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="685a9-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

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

      <span data-ttu-id="685a9-138">Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken .</span><span class="sxs-lookup"><span data-stu-id="685a9-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="685a9-139">Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="685a9-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="685a9-140">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="685a9-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="685a9-141">**Ga als volgt**te werk: Selecteer **De eigenschappen** \> van het bericht **wijzigen stel het spamvertrouwensniveau (SCL) in.**</span><span class="sxs-lookup"><span data-stu-id="685a9-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="685a9-142">Configureer in het dialoogvenster **SCL opgeven** dat wordt weergegeven een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="685a9-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="685a9-143">Als u berichten als **spam**wilt markeren, selecteert u **6**.</span><span class="sxs-lookup"><span data-stu-id="685a9-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="685a9-144">De actie die u hebt **Spam** ingesteld voor spamfiltervonnissen in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="685a9-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="685a9-145">Om berichten te markeren als **Spam met een hoog vertrouwen** selecteert u **9**.</span><span class="sxs-lookup"><span data-stu-id="685a9-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="685a9-146">De actie die u hebt geconfigureerd voor spamfilteringsvonnissen met **een hoog vertrouwen** in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**</span><span class="sxs-lookup"><span data-stu-id="685a9-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="685a9-147">Zie [SCL (Spam confidence level) in Office 365](spam-confidence-levels.md)voor meer informatie over SCL-waarden.</span><span class="sxs-lookup"><span data-stu-id="685a9-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="685a9-148">Klik op **Opslaan** als u klaar bent</span><span class="sxs-lookup"><span data-stu-id="685a9-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="685a9-149">PowerShell gebruiken om een e-mailstroomregels te maken die bulke-mail filteren</span><span class="sxs-lookup"><span data-stu-id="685a9-149">Use PowerShell to create a mail flow rules that filter bulk email</span></span>

<span data-ttu-id="685a9-150">Gebruik de volgende syntaxis om een of beide regels voor e-mailstromen (reguliere expressies versus woorden) te maken:</span><span class="sxs-lookup"><span data-stu-id="685a9-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="685a9-151">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulk e-mailfiltering - RegEx' die dezelfde lijst met reguliere expressies van eerder in het onderwerp gebruikt om berichten in te stellen als **Spam.**</span><span class="sxs-lookup"><span data-stu-id="685a9-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="685a9-152">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulk e-mailfiltering - Woorden' die dezelfde lijst met woorden van eerder in het onderwerp gebruikt om berichten in te stellen als **spam met een hoog vertrouwen.**</span><span class="sxs-lookup"><span data-stu-id="685a9-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="685a9-153">Zie [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="685a9-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="685a9-154">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="685a9-154">How do you know this worked?</span></span>

<span data-ttu-id="685a9-155">Ga een van de volgende stappen uit om te controleren of u regels voor e-mail hebt geconfigureerd om bulke-mail te filteren:</span><span class="sxs-lookup"><span data-stu-id="685a9-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="685a9-156">Ga in de EAC naar **EAC-regels** \> **Rules** \> en selecteer](../../media/ITPro-EAC-EditIcon.png)de regel \> klik op Pictogram Bewerken **bewerken** ![en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="685a9-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="685a9-157">Vervang in \<PowerShell\> regelnaam door de naam van de regel en voer de volgende opdracht uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="685a9-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="685a9-158">Stuur vanuit een extern account een testbericht naar een getroffen ontvanger die een van de zinnen of tekstpatronen bevat en verifieer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="685a9-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
