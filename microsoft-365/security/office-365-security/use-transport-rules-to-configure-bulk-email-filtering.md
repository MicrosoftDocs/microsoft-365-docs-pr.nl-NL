---
title: Regels voor e-mailstroom gebruiken om bulke-mail te filteren
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
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (transportregels) kunnen gebruiken om bulkmail (grijze e-mail) te identificeren en te filteren in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 860c9a1af2cb560c4fd966b303501686a1cbfea7
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613310"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="bf97f-103">E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="bf97f-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="bf97f-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam en bulkmail (ook wel grijze e-mail genoemd).</span><span class="sxs-lookup"><span data-stu-id="bf97f-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="bf97f-105">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bf97f-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bf97f-106">Als u meer opties wilt om bulkmail te filteren, u regels voor e-mailstroom (ook wel transportregels genoemd) maken om te zoeken naar tekstpatronen of zinnen die vaak in bulkpost worden gevonden en deze berichten als spam markeren.</span><span class="sxs-lookup"><span data-stu-id="bf97f-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="bf97f-107">Zie Wat is het [verschil tussen ongewenste e-mail en bulke-mail en](what-s-the-difference-between-junk-email-and-bulk-email.md) [bulkklachtniveau (BCL) in EOP](bulk-complaint-level-values.md)voor meer informatie over bulkmail.</span><span class="sxs-lookup"><span data-stu-id="bf97f-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="bf97f-108">In dit onderwerp wordt uitgelegd hoe u deze regels voor e-mailstroom maakt in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="bf97f-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bf97f-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="bf97f-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bf97f-110">U moet machtigingen krijgen voordat u deze procedures uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="bf97f-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="bf97f-111">Zie in Exchange Online de vermelding 'E-mailstroom' in [Functiemachtigingen in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)</span><span class="sxs-lookup"><span data-stu-id="bf97f-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="bf97f-112">In standalone EOP hebt u standaard de rol Transportregels nodig, die standaard is toegewezen aan de rollen OrganizationManagement, ComplianceManagement en RecordsManagement.</span><span class="sxs-lookup"><span data-stu-id="bf97f-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="bf97f-113">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bf97f-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="bf97f-114">Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om de EAC in Exchange Online te openen.</span><span class="sxs-lookup"><span data-stu-id="bf97f-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="bf97f-115">Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om de EAC in standalone EOP te openen.</span><span class="sxs-lookup"><span data-stu-id="bf97f-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="bf97f-116">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf97f-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bf97f-117">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf97f-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bf97f-118">Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en standalone EOP:</span><span class="sxs-lookup"><span data-stu-id="bf97f-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="bf97f-119">Regels voor e-mailstroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf97f-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="bf97f-120">Voorwaarden en uitzonderingen voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf97f-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="bf97f-121">Acties van de mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf97f-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="bf97f-122">De lijst met woorden en tekstpatronen die worden gebruikt om bulkmail in de voorbeelden te identificeren, is niet volledig; u indien nodig vermeldingen toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="bf97f-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="bf97f-123">Ze zijn echter een goed uitgangspunt.</span><span class="sxs-lookup"><span data-stu-id="bf97f-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="bf97f-124">Het zoeken naar woorden of tekstpatronen in het onderwerp of andere koptekstvelden in het bericht vindt plaats *nadat* het bericht is gedecodeerd van de MIME-methode voor inhoudsoverdracht die is gebruikt om het binaire bericht tussen SMTP-servers in ASCII-tekst te verzenden.</span><span class="sxs-lookup"><span data-stu-id="bf97f-124">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="bf97f-125">U geen voorwaarden of uitzonderingen gebruiken om te zoeken naar de ruwe (meestal Base64) gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.</span><span class="sxs-lookup"><span data-stu-id="bf97f-125">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="bf97f-126">De volgende procedures markeren een bulkbericht als spam voor uw hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="bf97f-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="bf97f-127">U echter een andere voorwaarde toevoegen om deze regels alleen toe te passen op specifieke ontvangers, zodat u agressieve filtering gebruiken op een paar, zeer gerichte gebruikers, terwijl de rest van uw gebruikers (die meestal de bulke-mail krijgen waarvoor ze zich hebben aangemeld) geen invloed hebben gehad.</span><span class="sxs-lookup"><span data-stu-id="bf97f-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="bf97f-128">De EAC gebruiken om regels voor e-mailstroom te maken die bulke-mail filteren</span><span class="sxs-lookup"><span data-stu-id="bf97f-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="bf97f-129">Ga in de EAC naar **Regels voor e-mailstromen** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="bf97f-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="bf97f-130">Klik **op** ![ pictogram Toevoegen en selecteer ](../../media/ITPro-EAC-AddIcon.png) **vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="bf97f-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="bf97f-131">Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="bf97f-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="bf97f-132">**Naam**: Voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="bf97f-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="bf97f-133">Klik op **Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="bf97f-133">Click **More Options**.</span></span>

   - <span data-ttu-id="bf97f-134">**Deze regel toepassen als:** Een van de volgende instellingen configureren om inhoud in berichten te zoeken met behulp van reguliere expressies (RegEx) of woorden of zinnen:</span><span class="sxs-lookup"><span data-stu-id="bf97f-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="bf97f-135">**Het onderwerp of het lichaam** \> **onderwerp of hoofdtekst komt overeen met deze tekstpatronen:** voer in het dialoogvenster **Woorden of zinnen opgeven** een van de volgende waarden in, klik op Pictogram **toevoegen** en herhaal totdat u alle waarden ![ hebt ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="bf97f-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="bf97f-136">Als u een item wilt bewerken, selecteert u het item en **klikt** u op ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken .</span><span class="sxs-lookup"><span data-stu-id="bf97f-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="bf97f-137">Als u een item wilt **Remove** verwijderen, selecteert u deze en klikt u op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="bf97f-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="bf97f-138">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="bf97f-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="bf97f-139">**Het onderwerp of het lichaam** \> **onderwerp of hoofdtekst bevat een van deze woorden:** Voer in het dialoogvenster **Woorden of zinnen opgeven** een van de volgende waarden in, klik op Pictogram **toevoegen** en herhaal totdat u alle waarden hebt ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="bf97f-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="bf97f-140">Als u een item wilt bewerken, selecteert u het item en **klikt** u op ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken .</span><span class="sxs-lookup"><span data-stu-id="bf97f-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="bf97f-141">Als u een item wilt **Remove** verwijderen, selecteert u deze en klikt u op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="bf97f-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="bf97f-142">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="bf97f-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="bf97f-143">**Ga als volgt te**werk : Selecteer **De berichteigenschappen** \> **wijzigen, het spamvertrouwensniveau (SCL) instellen.**</span><span class="sxs-lookup"><span data-stu-id="bf97f-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="bf97f-144">Configureer in het dialoogvenster **SCL opgeven** dat wordt weergegeven een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="bf97f-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="bf97f-145">Als u berichten als **spam wilt**markeren, selecteert u **6**.</span><span class="sxs-lookup"><span data-stu-id="bf97f-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="bf97f-146">De actie die u hebt geconfigureerd voor **het** filteren van spam in uw antispambeleid wordt toegepast op de berichten (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="bf97f-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="bf97f-147">Als u berichten markeert als **spam met een hoog vertrouwen,** selecteert u **9**.</span><span class="sxs-lookup"><span data-stu-id="bf97f-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="bf97f-148">De actie die u hebt geconfigureerd voor uitspraken met **een hoog vertrouwensspamfiltering** in uw antispambeleid, wordt toegepast op de berichten (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**</span><span class="sxs-lookup"><span data-stu-id="bf97f-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="bf97f-149">Zie [Spam confidence level (SCL) in EOP voor](spam-confidence-levels.md)meer informatie over SCL-waarden.</span><span class="sxs-lookup"><span data-stu-id="bf97f-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="bf97f-150">Klik op **Opslaan** als u klaar bent</span><span class="sxs-lookup"><span data-stu-id="bf97f-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="bf97f-151">PowerShell gebruiken om regels voor e-mailstroom te maken die bulke-mail filteren</span><span class="sxs-lookup"><span data-stu-id="bf97f-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="bf97f-152">Gebruik de volgende syntaxis om een of beide regels voor de e-mailstroom (reguliere expressies versus woorden) te maken:</span><span class="sxs-lookup"><span data-stu-id="bf97f-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="bf97f-153">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulk e-mailfiltering - RegEx' die dezelfde lijst met reguliere expressies van eerder in het onderwerp gebruikt om berichten in te stellen als **Spam.**</span><span class="sxs-lookup"><span data-stu-id="bf97f-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="bf97f-154">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam 'Bulk e-mailfiltering - Woorden' die dezelfde lijst met woorden van eerder in het onderwerp gebruikt om berichten in te stellen als **spam met een hoog vertrouwen.**</span><span class="sxs-lookup"><span data-stu-id="bf97f-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="bf97f-155">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="bf97f-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bf97f-156">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="bf97f-156">How do you know this worked?</span></span>

<span data-ttu-id="bf97f-157">Als u wilt controleren of u regels voor e-mailstromen hebt geconfigureerd om bulke-mail te filteren, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="bf97f-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="bf97f-158">Ga in de EAC naar **E-mailstroomregels** \> **Rules** \> selecteer de regel \> klik op **Edit** ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="bf97f-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="bf97f-159">Vervang in PowerShell \<Rule Name\> de naam van de regel en voer de volgende opdracht uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="bf97f-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="bf97f-160">Verzend vanuit een extern account een testberichten naar een getroffen ontvanger die een van de zinnen of tekstpatronen bevat en verifieer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="bf97f-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
