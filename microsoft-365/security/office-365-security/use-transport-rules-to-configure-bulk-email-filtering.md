---
title: Regels voor e-mail stroom gebruiken om bulk berichten te filteren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over het gebruik van regels voor e-mail stroom (transportregels) voor het identificeren en filteren van bulkmail (grijze e-mail) in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82a93cdc7375468748f241e2d15d729811095330
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600307"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="19447-103">E-mailstroomregels gebruiken om bulk-e-mail te filteren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="19447-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="19447-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP-organisaties zonder Exchange Online-postvakken), EOP maakt gebruik van Antispambeleid (ook wel een spamfilter beleid of inhouds filter beleid) om binnenkomende berichten te scannen voor spam en bulkmail (ook wel grijze e-mail genoemd).</span><span class="sxs-lookup"><span data-stu-id="19447-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="19447-105">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="19447-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="19447-106">Als u meer opties voor bulkmail wilt filteren, kunt u e-mail stroom regels (ook wel transport-regels genoemd) maken om te zoeken naar tekstpatronen of woordgroepen die vaak worden gevonden in bulkmail en om die berichten als spam te markeren.</span><span class="sxs-lookup"><span data-stu-id="19447-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="19447-107">Zie voor meer informatie over bulkmail [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) en [bulk klachten niveau (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="19447-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="19447-108">In dit onderwerp wordt uitgelegd hoe u deze regels voor de e-mail stroom maakt in het Exchange Admin Center (SBV) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="19447-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="19447-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="19447-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="19447-110">U moet machtigingen toegewezen hebben voordat u de volgende procedures kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="19447-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="19447-111">In Exchange Online raadpleegt u de invoer voor de e-mail stroom in [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="19447-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="19447-112">In zelfstandige EOP hebt u de rol Transport regel nodig, die standaard is toegewezen aan de rollen de organizationmanagement, ComplianceManagement en RecordsManagement.</span><span class="sxs-lookup"><span data-stu-id="19447-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="19447-113">Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="19447-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="19447-114">Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om het SBV te openen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="19447-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="19447-115">Als u het Exchange-Beheercentrum in standalone EOP wilt openen, raadpleegt u [Exchange Admin Center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="19447-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="19447-116">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19447-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="19447-117">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19447-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="19447-118">Zie de volgende onderwerpen voor meer informatie over regels voor e-mail stroom in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="19447-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="19447-119">Regels voor e-mail stroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19447-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="19447-120">Voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19447-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="19447-121">Acties voor e-mail stroom regels in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19447-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="19447-122">De lijst met woorden en tekstpatronen die worden gebruikt voor het identificeren van bulkmail in de voorbeelden zijn niet volledig; u kunt zo nodig gegevens toevoegen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="19447-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="19447-123">Maar wel een goed beginpunt.</span><span class="sxs-lookup"><span data-stu-id="19447-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="19447-124">De zoekfunctie voor woorden of tekstpatronen in het onderwerp of andere koptekstvelden in het bericht doet zich voor *Wanneer* het bericht is verwijderd uit de versleutelingsmethode MIME-inhoudsoverdracht die werd gebruikt om het binaire bericht te verzenden tussen SMTP-servers in ASCII-tekst.</span><span class="sxs-lookup"><span data-stu-id="19447-124">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="19447-125">U kunt voorwaarden of uitzonderingen niet gebruiken om te zoeken naar de gecodeerde waarden van het onderwerp of andere koptekstvelden in berichten.</span><span class="sxs-lookup"><span data-stu-id="19447-125">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="19447-126">In de volgende procedures wordt een bulk bericht als spam voor de hele organisatie gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="19447-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="19447-127">U kunt echter nog een voorwaarde toevoegen om deze regels alleen op specifieke geadresseerden toe te passen, zodat u een zeer sterk bedoelende gebruiker kunt gebruiken, terwijl de rest van de gebruikers (die het grootste e-mailbericht waartoe de e-mail wordt verzonden) niet worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="19447-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="19447-128">Het Exchange-Beheercentrum gebruiken om grote hoeveelheden e-mail te filteren</span><span class="sxs-lookup"><span data-stu-id="19447-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="19447-129">Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="19447-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="19447-130">Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="19447-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="19447-131">Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="19447-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="19447-132">**Naam**: Typ een unieke, beschrijvende naam voor de regel.</span><span class="sxs-lookup"><span data-stu-id="19447-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="19447-133">Klik op **meer opties**.</span><span class="sxs-lookup"><span data-stu-id="19447-133">Click **More Options**.</span></span>

   - <span data-ttu-id="19447-134">**Deze regel toepassen als**: een van de volgende instellingen configureren om inhoud in berichten te zoeken met behulp van reguliere expressies (regex) of woorden of woordgroepen:</span><span class="sxs-lookup"><span data-stu-id="19447-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="19447-135">**Het onderwerp of de hoofdtekst** \> **onderwerp of hoofdtekst komt overeen met deze tekstpatronen**: Typ een van de volgende waarden in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven **, klik op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en herhaal dit tot u alle waarden hebt ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="19447-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="19447-136">Als u een vermelding wilt bewerken, selecteert u **Edit** deze en klikt u op ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="19447-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="19447-137">Als u een vermelding wilt verwijderen, selecteert u deze **en klikt u** op het ![ pictogram verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="19447-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="19447-138">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="19447-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="19447-139">**Het onderwerp of de hoofdtekst** \> het **onderwerp of de hoofdtekst bevat een of meer van deze woorden**: Typ een van de volgende waarden in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven **, klik op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en herhaal dit tot u alle waarden hebt ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="19447-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="19447-140">Als u een vermelding wilt bewerken, selecteert u **Edit** deze en klikt u op ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="19447-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="19447-141">Als u een vermelding wilt verwijderen, selecteert u deze **en klikt u** op het ![ pictogram verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="19447-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="19447-142">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="19447-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="19447-143">**Ga als volgt**te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="19447-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="19447-144">In het dialoogvenster **SCL opgeven** dat wordt weergegeven, configureert u een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="19447-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="19447-145">Selecteer **6**om berichten als **spam**te markeren.</span><span class="sxs-lookup"><span data-stu-id="19447-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="19447-146">De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** Verdicts in uw Antispambeleid op de berichten (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="19447-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="19447-147">Als u berichten wilt markeren als **spam van hoge betrouwbaarheid** , selecteert u **9**.</span><span class="sxs-lookup"><span data-stu-id="19447-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="19447-148">De actie die u hebt geconfigureerd voor het filteren van **spam** filteren Verdicts in uw Antispambeleid, wordt op de berichten toegepast (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).</span><span class="sxs-lookup"><span data-stu-id="19447-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="19447-149">Zie voor meer informatie over SCL-waarden [spam niveau voor spam (SCL) in EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="19447-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="19447-150">Wanneer u klaar bent, klikt u op **Opslaan** .</span><span class="sxs-lookup"><span data-stu-id="19447-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="19447-151">PowerShell gebruiken om regels voor e-mail stroom te maken waarmee bulk berichten worden gefilterd</span><span class="sxs-lookup"><span data-stu-id="19447-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="19447-152">Gebruik de volgende syntaxis om een of beide regels voor de e-mail stroom te maken (reguliere expressies en. woorden):</span><span class="sxs-lookup"><span data-stu-id="19447-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="19447-153">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam ' bulksgewijze e-mail filtering ', die dezelfde lijst met reguliere expressies gebruikt, van eerder in het onderwerp om berichten in te stellen als **spam**.</span><span class="sxs-lookup"><span data-stu-id="19447-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="19447-154">In dit voorbeeld wordt een nieuwe regel gemaakt met de naam ' filteren van bulk-e-mail filteren-woorden ' waarbij de lijst met woorden van eerder in het onderwerp wordt gebruikt voor het instellen van berichten als **spam van hoge betrouwbaarheid**.</span><span class="sxs-lookup"><span data-stu-id="19447-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="19447-155">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="19447-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="19447-156">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="19447-156">How do you know this worked?</span></span>

<span data-ttu-id="19447-157">Voer een van de volgende stappen uit om te controleren of u de e-mail stroom regels hebt geconfigureerd voor het filteren van bulk-e-mail:</span><span class="sxs-lookup"><span data-stu-id="19447-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="19447-158">Ga in het Exchange-Beheercentrum naar **e-mail stroom** \> **regels** \> , selecteer de regel Klik op bewerkings \> pictogram **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="19447-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="19447-159">In PowerShell vervangt \<Rule Name\> u de naam van de regel en voert u de volgende opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="19447-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="19447-160">Verstuur via een extern account een testbericht naar een geadresseerde die een van de woordgroepen of tekstpatronen bevat, en controleer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="19447-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
