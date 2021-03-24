---
title: EOP configureren voor ongewenste e-mail in hybride omgevingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze spam kunnen doorverrouteeren naar mappen met ongewenste e-mail van gebruikers in een hybride omgeving van Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060070"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="8dd97-103">Zelfstandige EOP configureren om spam te verzenden naar de map Ongewenste e-mail in hybride omgevingen</span><span class="sxs-lookup"><span data-stu-id="8dd97-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8dd97-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8dd97-104">**Applies to**</span></span>
-  [<span data-ttu-id="8dd97-105">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8dd97-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="8dd97-106">Dit onderwerp is alleen beschikbaar voor zelfstandige EOP-klanten in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="8dd97-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="8dd97-107">Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="8dd97-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="8dd97-108">Als u een zelfstandige EOP-klant (Exchange Online Protection) bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie zo configureren dat de spamfilters van EOP worden herkend en vertaald, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten naar de map Ongewenste e-mail kan verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="8dd97-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="8dd97-109">In het bijzonder moet u regels voor e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden voor het vinden van berichten met een van de volgende EOP-antispamkoppen en -waarden, en acties die het betrouwbaarheidsniveau voor spam (SCL) van deze berichten instellen op 6:</span><span class="sxs-lookup"><span data-stu-id="8dd97-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="8dd97-110">`X-Forefront-Antispam-Report: SFV:SPM` (bericht gemarkeerd als spam door spamfilters)</span><span class="sxs-lookup"><span data-stu-id="8dd97-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="8dd97-111">`X-Forefront-Antispam-Report: SFV:SKS` (bericht dat is gemarkeerd als spam door e-mailstroomregels in EOP voordat spam wordt gefilterd)</span><span class="sxs-lookup"><span data-stu-id="8dd97-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="8dd97-112">`X-Forefront-Antispam-Report: SFV:SKB` (bericht dat is gemarkeerd als spam door spamfilters omdat het e-mailadres of e-maildomein van de afzender in de lijst met geblokkeerde afzenders of de geblokkeerde domeinlijst in EOP staat)</span><span class="sxs-lookup"><span data-stu-id="8dd97-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="8dd97-113">Zie Kopteksten voor spamberichten voor meer informatie over deze [koptekstwaarden.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="8dd97-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="8dd97-114">In dit onderwerp wordt beschreven hoe u deze e-mailstroomregels maakt in het Exchange-beheercentrum (EAC) en in de Exchange Management Shell (Exchange PowerShell) in de on-premises Exchange-organisatie.</span><span class="sxs-lookup"><span data-stu-id="8dd97-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="8dd97-115">In plaats van de berichten te verzenden naar de map Ongewenste e-mail van de on-premises gebruiker, kunt u antispambeleid configureren in EOP om spamberichten in EOP in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="8dd97-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="8dd97-116">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8dd97-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8dd97-117">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8dd97-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8dd97-118">U moet machtigingen krijgen toegewezen in de on-premises Exchange-omgeving voordat u deze procedures kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="8dd97-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="8dd97-119">U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer** en **Recordsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="8dd97-120">Zie Leden toevoegen aan [een rollengroep voor meer informatie.](/Exchange/permissions/role-group-members#add-members-to-a-role-group)</span><span class="sxs-lookup"><span data-stu-id="8dd97-120">For more information, see [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="8dd97-121">Als en wanneer een bericht wordt bezorgd in de map Ongewenste e-mail in een on-premises Exchange-organisatie wordt bepaald door een combinatie van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8dd97-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="8dd97-122">De _parameterwaarde SCLJunkThreshold_ op de [cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) in de Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8dd97-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="8dd97-123">De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet bezorgen in de map Ongewenste e-mail van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8dd97-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="8dd97-124">De _parameterwaarde SCLJunkThreshold_ op de [cmdlet](/powershell/module/exchange/set-mailbox) Postvak instellen in de Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8dd97-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="8dd97-125">De standaardwaarde is leeg ($null), wat betekent dat de organisatieinstelling wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8dd97-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="8dd97-126">Zie [SCL-drempels (Exchange spam confidence level) voor meer informatie.](/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="8dd97-126">For details, see [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="8dd97-127">Of de regel ongewenste e-mail is ingeschakeld in het postvak (de _parameterwaarde_ ingeschakeld is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Exchange Management Shell).</span><span class="sxs-lookup"><span data-stu-id="8dd97-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="8dd97-128">Het is de regel voor ongewenste e-mail die het bericht na de bezorging naar de map Ongewenste e-mail verplaatst.</span><span class="sxs-lookup"><span data-stu-id="8dd97-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="8dd97-129">Standaard is de regel ongewenste e-mail ingeschakeld in postvakken.</span><span class="sxs-lookup"><span data-stu-id="8dd97-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="8dd97-130">Zie [Exchange-antispaminstellingen configureren voor postvakken](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8dd97-130">For more information, see [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="8dd97-131">Zie [Exchange-beheercentrum in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center)om de EAC op een Exchange Server te openen.</span><span class="sxs-lookup"><span data-stu-id="8dd97-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="8dd97-132">Zie De Exchange Management Shell openen om de Exchange Management Shell [te openen.](/powershell/exchange/open-the-exchange-management-shell)</span><span class="sxs-lookup"><span data-stu-id="8dd97-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="8dd97-133">Zie de volgende onderwerpen voor meer informatie over e-mailstroomregels in on-premises Exchange:</span><span class="sxs-lookup"><span data-stu-id="8dd97-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="8dd97-134">Regels voor e-mailstroom in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8dd97-134">Mail flow rules in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="8dd97-135">Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8dd97-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="8dd97-136">Acties voor e-mailstroomregel in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8dd97-136">Mail flow rule actions in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="8dd97-137">Gebruik de EAC om regels voor e-mailstroom te maken die de SCL van EOP-spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="8dd97-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="8dd97-138">Ga in het EAC naar **E-mailstroomregels.** \> </span><span class="sxs-lookup"><span data-stu-id="8dd97-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="8dd97-139">Klik **op Pictogram** Toevoegen toevoegen en selecteer Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken** in de vervolgkeuzepagina die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8dd97-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="8dd97-140">Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="8dd97-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="8dd97-141">**Naam:** Voer een unieke, beschrijvende naam in voor de regel.</span><span class="sxs-lookup"><span data-stu-id="8dd97-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="8dd97-142">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8dd97-142">For example:</span></span>

     - <span data-ttu-id="8dd97-143">EOP SFV:SPM naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="8dd97-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="8dd97-144">EOP SFV:SKS naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="8dd97-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="8dd97-145">EOP SFV:SKB naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="8dd97-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="8dd97-146">Klik **op Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-146">Click **More Options**.</span></span>

   - <span data-ttu-id="8dd97-147">**Pas deze regel toe als**: Selecteer Een **berichtkop** \> **bevat een van deze woorden.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="8dd97-148">Voer de **volgende stappen uit** in de tekstkop Enter met de tekstzin Enter die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="8dd97-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="8dd97-149">Klik **op Tekst invoeren.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-149">Click **Enter text**.</span></span> <span data-ttu-id="8dd97-150">Typ in **het dialoogvenster Naam van koptekst** opgeven dat wordt weergegeven **X-Forefront-Antispam-Report** en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="8dd97-151">Klik **op Woorden invoeren.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-151">Click  **Enter words**.</span></span> <span data-ttu-id="8dd97-152">Typ **in** het dialoogvenster Woorden of woordgroepen opgeven dat wordt weergegeven een van de EOP-waarden voor spamkoppen **(SFV:SPM,** **SFV:SKS** of **SFV:SKB),** klik op Pictogram Toevoegen toevoegen en klik vervolgens op  ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**</span><span class="sxs-lookup"><span data-stu-id="8dd97-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="8dd97-153">**Ga als volgt** te werk: Selecteer **De eigenschappen van het bericht wijzigen** Het \> **betrouwbaarheidsniveau voor spam instellen (SCL).**</span><span class="sxs-lookup"><span data-stu-id="8dd97-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="8dd97-154">Selecteer **6** (de standaardwaarde is **5)** in het dialoogvenster **SCL** opgeven dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8dd97-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="8dd97-155">Wanneer u klaar bent, klikt u op **Opslaan**</span><span class="sxs-lookup"><span data-stu-id="8dd97-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="8dd97-156">Herhaal deze stappen voor de resterende EOP-waarden voor spam **(SFV:SPM,** **SFV:SKS** of **SFV:SKB).**</span><span class="sxs-lookup"><span data-stu-id="8dd97-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="8dd97-157">Gebruik de Exchange Management Shell om e-mailstroomregels te maken die de SCL van EOP-spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="8dd97-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="8dd97-158">Gebruik de volgende syntaxis om de drie regels voor de e-mailstroom te maken:</span><span class="sxs-lookup"><span data-stu-id="8dd97-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="8dd97-159">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8dd97-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="8dd97-160">Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8dd97-160">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8dd97-161">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="8dd97-161">How do you know this worked?</span></span>

<span data-ttu-id="8dd97-162">Als u wilt controleren of u zelfstandige EOP hebt geconfigureerd om spam te verzenden naar de map Ongewenste e-mail in een hybride omgeving, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="8dd97-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="8dd97-163">Ga in het EAC naar **E-mailstroomregels,** selecteer de regel en klik vervolgens op Pictogram Bewerken bewerken om \> de instellingen  ![ te ](../../media/ITPro-EAC-EditIcon.png) verifiëren.</span><span class="sxs-lookup"><span data-stu-id="8dd97-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="8dd97-164">Vervang in de Exchange Management Shell de naam van de e-mailstroomregel en rul de volgende opdracht om \<RuleName\> de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="8dd97-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="8dd97-165">In een extern e-mailsysteem dat uitgaande berichten niet scant op **spam,** verzendt u een algemene test voor ongewenste bulk-e-mail (GTUBE) naar een getroffen geadresseerde en bevestigt u dat het bericht is bezorgd in de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8dd97-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="8dd97-166">Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.</span><span class="sxs-lookup"><span data-stu-id="8dd97-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="8dd97-167">Als u een GTUBE-bericht wilt verzenden, moet u de volgende tekst in de kop van een e-mailbericht opnemen op één regel, zonder spaties of regel-einden:</span><span class="sxs-lookup"><span data-stu-id="8dd97-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```