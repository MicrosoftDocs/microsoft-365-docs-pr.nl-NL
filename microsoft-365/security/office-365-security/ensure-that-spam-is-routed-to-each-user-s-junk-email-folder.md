---
title: EOP configureren voor ongewenste spam in hybride omgevingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u spam stuurt naar mappen voor ongewenste E-mail in een Exchange Online Protection hybride omgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 76003f18009ebf9159f01d916cdaf38b50a213d1
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350337"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="c4037-103">Zelfstandige EOP configureren voor het afleveren van spam op de map Ongewenste E-mail in hybride omgevingen</span><span class="sxs-lookup"><span data-stu-id="c4037-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="c4037-104">Dit onderwerp is alleen voor zelfstandige EOP-klanten in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="c4037-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="c4037-105">Dit onderwerp is niet van toepassing op Microsoft 365-klanten met postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c4037-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="c4037-106">Als u een zelfstandige Exchange Online Protection-klant (EOP) hebt in een hybride omgeving, moet u uw on-premises Exchange-organisatie configureren voor het herkennen en vertalen van de spamfilters Verdicts van EOP, zodat de regel voor ongewenste e-mail in het on-premises postvak berichten kan verplaatsen naar de map Ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="c4037-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="c4037-107">U moet specifiek voor het maken van een e-mail stroom regels (ook wel transport-regels genoemd) in uw on-premises Exchange-organisatie met voorwaarden waarmee u berichten vindt met een van de volgende EOP-antispam koppen en-waarden, en acties waarmee het spam niveau van deze berichten wordt ingesteld op 6:</span><span class="sxs-lookup"><span data-stu-id="c4037-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="c4037-108">`X-Forefront-Antispam-Report: SFV:SPM` (bericht gemarkeerd als spam door spam te filteren)</span><span class="sxs-lookup"><span data-stu-id="c4037-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="c4037-109">`X-Forefront-Antispam-Report: SFV:SKS` (bericht gemarkeerd als spam door regels voor de e-mail stroom in EOP voordat spam wordt gefilterd)</span><span class="sxs-lookup"><span data-stu-id="c4037-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="c4037-110">`X-Forefront-Antispam-Report: SFV:SKB` (bericht is gemarkeerd als spam door spam te filteren vanwege het e-mailadres of e-mail domein van de afzender in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in EOP)</span><span class="sxs-lookup"><span data-stu-id="c4037-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="c4037-111">Zie [anti spambericht koppen](anti-spam-message-headers.md)voor meer informatie over deze koptekst waarden.</span><span class="sxs-lookup"><span data-stu-id="c4037-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="c4037-112">In dit onderwerp wordt beschreven hoe u deze regels voor e-mail stroom kunt maken in het Exchange-Beheercentrum en in de Exchange-beheer shell (Exchange PowerShell) in de on-premises Exchange-organisatie.</span><span class="sxs-lookup"><span data-stu-id="c4037-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="c4037-113">In plaats van de berichten naar de map Ongewenste E-mail van de gebruiker te bezorgen, kunt u Antispambeleid in EOP configureren voor het gebruiken van spamberichten in EOP.</span><span class="sxs-lookup"><span data-stu-id="c4037-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="c4037-114">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4037-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4037-115">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="c4037-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c4037-116">U moet machtigingen voor de on-premises Exchange-omgeving worden toegewezen voordat u deze procedures kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="c4037-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="c4037-117">Specifiek moet u de rol van **transport regels** toewijzen, die aan de rollen voor **Organisatiebeheer**, **Compliance Management**, en het **beheer van recordbeheer** standaard is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c4037-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="c4037-118">Zie [leden aan een rollen groep toevoegen](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4037-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="c4037-119">Als en wanneer een bericht wordt bezorgd in de map Ongewenste E-mail in een on-premises Exchange-organisatie, wordt bepaald door een combinatie van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="c4037-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="c4037-120">De waarde van _SCLJunkThreshold_ -parameter in de cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in de Exchange-beheer shell.</span><span class="sxs-lookup"><span data-stu-id="c4037-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="c4037-121">De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht naar de map Ongewenste e-mail van de gebruiker verzorgt.</span><span class="sxs-lookup"><span data-stu-id="c4037-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="c4037-122">De waarde van de _SCLJunkThreshold_ -parameter in de cmdlet [set-mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in de Exchange-beheer shell.</span><span class="sxs-lookup"><span data-stu-id="c4037-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="c4037-123">De standaardwaarde is leeg ($null), wat betekent dat de organisatie-instelling wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c4037-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="c4037-124">Zie [drempelwaarden voor spam niveau van Exchange (SCL)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4037-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="c4037-125">Of de regel voor ongewenste e-mail is ingeschakeld voor het postvak (de _ingeschakelde_ parameterwaarde is $True op de cmdlet [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Exchange-beheer shell).</span><span class="sxs-lookup"><span data-stu-id="c4037-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="c4037-126">Het is de regel voor ongewenste e-mail waarmee het bericht na ontvangst naar de map Ongewenste E-mail wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="c4037-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="c4037-127">Standaard is de regel voor ongewenste e-mail ingeschakeld voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="c4037-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="c4037-128">Zie [Exchange spam instellingen in postvakken configureren](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4037-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="c4037-129">Zie [Exchange-Beheercentrum in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)om de versie van het Beheercentrum te openen op een Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="c4037-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="c4037-130">Zie [de Exchange-beheer shell openen](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)voor informatie over het openen van de Exchange-beheer shell.</span><span class="sxs-lookup"><span data-stu-id="c4037-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="c4037-131">Zie de volgende onderwerpen voor meer informatie over regels voor e-mail stroom in on-premises Exchange:</span><span class="sxs-lookup"><span data-stu-id="c4037-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="c4037-132">Regels voor e-mail stroom in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c4037-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="c4037-133">Voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c4037-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="c4037-134">Acties voor e-mail stroom regels in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c4037-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="c4037-135">Het Exchange-Beheercentrum gebruiken om regels voor de e-mail stroom in te stellen voor het maken van de SCL van EOP spamberichten</span><span class="sxs-lookup"><span data-stu-id="c4037-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="c4037-136">Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="c4037-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c4037-137">Klik **op** ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer **een nieuwe regel maken** in de vervolgkeuzelijst die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c4037-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="c4037-138">Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="c4037-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c4037-139">**Naam**: Typ een unieke, beschrijvende naam voor de regel.</span><span class="sxs-lookup"><span data-stu-id="c4037-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="c4037-140">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c4037-140">For example:</span></span>

     - <span data-ttu-id="c4037-141">EOP SFV: SPM to SCL 6</span><span class="sxs-lookup"><span data-stu-id="c4037-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="c4037-142">EOP SFV: SKS naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="c4037-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="c4037-143">EOP SFV: SKB naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="c4037-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="c4037-144">Klik op **meer opties**.</span><span class="sxs-lookup"><span data-stu-id="c4037-144">Click **More Options**.</span></span>

   - <span data-ttu-id="c4037-145">**Deze regel toepassen als**: Selecteer **een kop van het bericht** \> **bevat een van deze woorden**.</span><span class="sxs-lookup"><span data-stu-id="c4037-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="c4037-146">Voer de volgende stappen uit in de **kop tekst** invoeren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="c4037-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="c4037-147">Klik op **tekst invoeren**.</span><span class="sxs-lookup"><span data-stu-id="c4037-147">Click **Enter text**.</span></span> <span data-ttu-id="c4037-148">Voer in het dialoogvenster **opgegeven naam van de koptekst opgeven de tekst** **X-Forefront-spam-report** in en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4037-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="c4037-149">Klik op  **woorden invoeren**.</span><span class="sxs-lookup"><span data-stu-id="c4037-149">Click  **Enter words**.</span></span> <span data-ttu-id="c4037-150">Voer in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven een van de EOP spam waarden van de spam (**SFV: SPM**, **SFV: sks**of **SFV: SKB**) in **, klik op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4037-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="c4037-151">**Ga als volgt**te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="c4037-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="c4037-152">Selecteer in het dialoogvenster **SCL opgeven** dat wordt weergegeven de optie **6** (de standaardwaarde is **5**).</span><span class="sxs-lookup"><span data-stu-id="c4037-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="c4037-153">Wanneer u klaar bent, klikt u op **Opslaan** .</span><span class="sxs-lookup"><span data-stu-id="c4037-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="c4037-154">Herhaal deze stappen voor de resterende EOP spam verdict-waarden (**SFV: SPM**, **SFV: sks**of **SFV: SKB**).</span><span class="sxs-lookup"><span data-stu-id="c4037-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="c4037-155">De Exchange-beheer shell gebruiken om regels voor de e-mail stroom te maken die de SCL van EOP spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="c4037-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="c4037-156">Gebruik de volgende syntaxis om de drie e-mail stroom regels te maken:</span><span class="sxs-lookup"><span data-stu-id="c4037-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="c4037-157">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c4037-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="c4037-158">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="c4037-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c4037-159">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="c4037-159">How do you know this worked?</span></span>

<span data-ttu-id="c4037-160">Voer een van de volgende stappen uit om te controleren of u zelfstandige EOP hebt geconfigureerd voor het afleveren van spam in de map Ongewenste E-mail in hybride omgeving:</span><span class="sxs-lookup"><span data-stu-id="c4037-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="c4037-161">Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**, selecteer de regel en klik vervolgens op **Edit** ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-EditIcon.png) om de instellingen te controleren.</span><span class="sxs-lookup"><span data-stu-id="c4037-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="c4037-162">In de Exchange-beheer shell vervangt \<RuleName\> u de naam van de e-mail stroom regel door de naam van de e-mail stroom regel en rul u de volgende opdracht om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="c4037-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="c4037-163">In een extern e-mailsysteem **dat uitgaande berichten voor spam niet scant**, stuurt u een algemene test voor ongevraagde E-mail (GTUBE) naar een geadresseerde en bevestigt u dat deze wordt bezorgd in de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="c4037-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="c4037-164">Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.</span><span class="sxs-lookup"><span data-stu-id="c4037-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="c4037-165">Als u een GTUBE bericht wilt verzenden, moet u de volgende tekst opnemen in de hoofdtekst van een e-mailbericht op een enkele regel, zonder spaties of regeleinden:</span><span class="sxs-lookup"><span data-stu-id="c4037-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
