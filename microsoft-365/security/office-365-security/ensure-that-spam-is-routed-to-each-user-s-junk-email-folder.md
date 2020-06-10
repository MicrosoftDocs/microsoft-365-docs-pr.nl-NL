---
title: EOP configureren voor ongewenste spam in hybride omgevingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze spam kunnen routeren naar ongewenste e-mailmappen van gebruikers in een hybride exchange-omgeving voor onlinebescherming.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d8ba6aae599ee4dd327bd1ec82b46e8f3ee3ca8
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679118"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="b4b53-103">Zelfstandige EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen</span><span class="sxs-lookup"><span data-stu-id="b4b53-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4b53-104">Dit onderwerp is alleen voor standalone EOP-klanten in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="b4b53-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="b4b53-105">Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="b4b53-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="b4b53-106">Als u een zelfstandige EOP-klant (Exchange Online Protection) bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie configureren om de uitspraken van EOP voor spamfilters te herkennen en te vertalen, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten naar de map Ongewenste e-mail kan verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="b4b53-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="b4b53-107">In het bijzonder moet u regels voor e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden die berichten vinden met een van de volgende EOP-antispamheaders en -waarden, en acties die het spamvertrouwensniveau (SCL) van die berichten instellen op 6:</span><span class="sxs-lookup"><span data-stu-id="b4b53-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="b4b53-108">`X-Forefront-Antispam-Report: SFV:SPM`(bericht gemarkeerd als spam door spamfiltering)</span><span class="sxs-lookup"><span data-stu-id="b4b53-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="b4b53-109">`X-Forefront-Antispam-Report: SFV:SKS`(bericht gemarkeerd als spam door e-mailstroomregels in EOP voordat spamfiltert)</span><span class="sxs-lookup"><span data-stu-id="b4b53-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="b4b53-110">`X-Forefront-Antispam-Report: SFV:SKB`(bericht gemarkeerd als spam door spamfiltering omdat het e-mailadres of e-maildomein van de afzender zich in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in EOP bevindt)</span><span class="sxs-lookup"><span data-stu-id="b4b53-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="b4b53-111">Zie [Antispamberichtenkoppen](anti-spam-message-headers.md)voor meer informatie over deze kopteksten.</span><span class="sxs-lookup"><span data-stu-id="b4b53-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="b4b53-112">In dit onderwerp wordt beschreven hoe u deze regels voor e-mailstroom maakt in het Exchange-beheercentrum (EAC) en in de Exchange Management Shell (Exchange PowerShell) in de on-premises Exchange-organisatie.</span><span class="sxs-lookup"><span data-stu-id="b4b53-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="b4b53-113">In plaats van de berichten te leveren aan de map Ongewenste e-mail van de on-premises gebruiker, u antispambeleid in EOP configureren om spamberichten in EOP in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="b4b53-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="b4b53-114">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b4b53-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b4b53-115">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b4b53-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b4b53-116">U moet machtigingen krijgen toegewezen in de on-premises Exchange-omgeving voordat u deze procedures uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b4b53-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="b4b53-117">In het bijzonder moet u de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliance Management**en **Records Management.**</span><span class="sxs-lookup"><span data-stu-id="b4b53-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="b4b53-118">Zie [Leden toevoegen aan een rolgroep voor](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b4b53-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="b4b53-119">Als en wanneer een bericht wordt bezorgd in de map Ongewenste e-mail in een on-premises Exchange-organisatie, wordt het beheerd door een combinatie van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b4b53-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="b4b53-120">De parameterwaarde _SCLJunkThreshold_ op de [cmdlet Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in de Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b4b53-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="b4b53-121">De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet leveren aan de map Ongewenste e-mail van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b4b53-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="b4b53-122">De parameterwaarde _SCLJunkThreshold_ op de cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in de Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b4b53-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="b4b53-123">De standaardwaarde is leeg ($null), wat betekent dat de organisatie-instelling wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b4b53-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="b4b53-124">Zie [SCL-drempels (Exchange spam confidence level) voor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b4b53-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="b4b53-125">Of de regel voor ongewenste e-mail is ingeschakeld in het postvak (de parameterwaarde _ingeschakeld_ is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Shell Exchange Management).</span><span class="sxs-lookup"><span data-stu-id="b4b53-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="b4b53-126">Het is de regel voor ongewenste e-mail die het bericht na levering daadwerkelijk naar de map Ongewenste e-mail verplaatst.</span><span class="sxs-lookup"><span data-stu-id="b4b53-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="b4b53-127">Standaard is de regel voor ongewenste e-mail ingeschakeld op postvakken.</span><span class="sxs-lookup"><span data-stu-id="b4b53-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="b4b53-128">Zie [Exchange-antispaminstellingen configureren voor postvakken](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b4b53-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="b4b53-129">Zie [Exchange-beheercentrum in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)als u de EAC op een Exchange Server wilt openen.</span><span class="sxs-lookup"><span data-stu-id="b4b53-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="b4b53-130">Zie De Shell voor [Exchange Management openen](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)als u de Shell voor Exchange Management wilt openen.</span><span class="sxs-lookup"><span data-stu-id="b4b53-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="b4b53-131">Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstroom in on-premises Exchange:</span><span class="sxs-lookup"><span data-stu-id="b4b53-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="b4b53-132">Regels voor e-mailstroom in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b4b53-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="b4b53-133">Voorwaarden en uitzonderingen voor e-mailstroomregel in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b4b53-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="b4b53-134">Acties van de e-mailstroomregel in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b4b53-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="b4b53-135">De EAC gebruiken om regels voor e-mailstroom te maken die de SCL van EOP-spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="b4b53-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="b4b53-136">Ga in de EAC naar **Regels voor e-mailstromen** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="b4b53-137">Klik **op** ![ pictogram Toevoegen toevoegen en selecteer Een ](../../media/ITPro-EAC-AddIcon.png) nieuwe regel **maken** in de vervolgkeuzelijst die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b4b53-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="b4b53-138">Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b4b53-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="b4b53-139">**Naam**: Voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="b4b53-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="b4b53-140">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b4b53-140">For example:</span></span>

     - <span data-ttu-id="b4b53-141">EOP SFV:SPM naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="b4b53-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="b4b53-142">EOP SFV:SKS naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="b4b53-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="b4b53-143">EOP SFV:SKB naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="b4b53-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="b4b53-144">Klik op **Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-144">Click **More Options**.</span></span>

   - <span data-ttu-id="b4b53-145">**Pas deze regel toe als**: Selecteer Een **berichtkoptekst** \> **bevat een van deze woorden**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="b4b53-146">Voer in de **tekstkop enter de woordenzin** invoeren die wordt weergegeven, de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="b4b53-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="b4b53-147">Klik **op Tekst invoeren**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-147">Click **Enter text**.</span></span> <span data-ttu-id="b4b53-148">Voer in het dialoogvenster **Koptekstnaam opgeven** dat wordt **weergegeven, X-Forefront-Antispam-Rapport in** en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="b4b53-149">Klik **op Woorden invoeren**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-149">Click  **Enter words**.</span></span> <span data-ttu-id="b4b53-150">Voer in het dialoogvenster **Woorden of zinnen opgeven** die wordt weergegeven, een van de EOP-spamkopwaarden in **(SFV:SPM**, **SFV:SKS**of **SFV:SKB),** **klik** op ![ pictogram Toevoegen en klik ](../../media/ITPro-EAC-AddIcon.png) vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4b53-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="b4b53-151">**Ga als volgt te**werk: **Selecteer De berichteigenschappen wijzigen** Stel het \> **spamvertrouwensniveau (SCL)** in .</span><span class="sxs-lookup"><span data-stu-id="b4b53-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="b4b53-152">Selecteer in het dialoogvenster **SCL opgeven** dat wordt weergegeven **6** (de standaardwaarde is **5).**</span><span class="sxs-lookup"><span data-stu-id="b4b53-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="b4b53-153">Klik op **Opslaan** als u klaar bent</span><span class="sxs-lookup"><span data-stu-id="b4b53-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="b4b53-154">Herhaal deze stappen voor de resterende EOP-spamoordeelwaarden **(SFV:SPM**, **SFV:SKS**of **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="b4b53-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="b4b53-155">De Exchange Management Shell gebruiken om regels voor e-mailstroom te maken die de SCL van EOP-spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="b4b53-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="b4b53-156">Gebruik de volgende syntaxis om de drie regels voor e-mailstroom te maken:</span><span class="sxs-lookup"><span data-stu-id="b4b53-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="b4b53-157">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b4b53-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="b4b53-158">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="b4b53-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b4b53-159">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="b4b53-159">How do you know this worked?</span></span>

<span data-ttu-id="b4b53-160">Als u wilt controleren of u zelfstandige EOP hebt geconfigureerd om spam te leveren aan de map Ongewenste e-mail in een hybride omgeving, voert u een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="b4b53-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="b4b53-161">Ga in de EAC naar **e-mailstroomregels,** \> **Rules**selecteer de regel en klik vervolgens op pictogram Bewerken bewerken om de instellingen **Edit** ![ te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.</span><span class="sxs-lookup"><span data-stu-id="b4b53-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="b4b53-162">Vervang in de Shell voor Exchange-beheer \<RuleName\> de naam van de e-mailstroomregel en regel de volgende opdracht om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="b4b53-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="b4b53-163">In een extern e-mailsysteem **dat geen uitgaande berichten scant voor spam, verzendt**u een GTUBE-bericht (Generic Test for Onsolitcited Bulk Email) naar een getroffen ontvanger en bevestigt u dat het wordt bezorgd in de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="b4b53-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="b4b53-164">Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.</span><span class="sxs-lookup"><span data-stu-id="b4b53-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="b4b53-165">Als u een GTUBE-bericht wilt verzenden, neemt u de volgende tekst op in de hoofdtekst van een e-mailbericht op één regel, zonder spaties of regeleinden:</span><span class="sxs-lookup"><span data-stu-id="b4b53-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
