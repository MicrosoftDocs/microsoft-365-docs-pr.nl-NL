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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het doorrouten van spam naar mappen voor ongewenste e-mail van gebruikers in een hybride omgeving van Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167117"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="957e6-103">Zelfstandige EOP configureren voor het bezorgen van spam naar de map Ongewenste e-mail in hybride omgevingen</span><span class="sxs-lookup"><span data-stu-id="957e6-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="957e6-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="957e6-104">**Applies to**</span></span>
-  [<span data-ttu-id="957e6-105">Zelfstandige versie van Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="957e6-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> <span data-ttu-id="957e6-106">Dit onderwerp is alleen voor zelfstandige EOP-klanten in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="957e6-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="957e6-107">Dit onderwerp is niet van toepassing op Microsoft 365-klanten met Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="957e6-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="957e6-108">Als u een zelfstandige klant van Exchange Online Protection (EOP) bent in een hybride omgeving, moet u uw on-premises Exchange-organisatie zo configureren dat de spamfilters van EOP worden herkend en vertaald, zodat berichten naar de map Ongewenste e-mail kunnen worden verplaatst met de regel voor ongewenste e-mail in het on-premises postvak.</span><span class="sxs-lookup"><span data-stu-id="957e6-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="957e6-109">U moet met name regels voor de e-mailstroom (ook wel transportregels genoemd) maken in uw on-premises Exchange-organisatie met voorwaarden voor het vinden van berichten met een van de volgende EOP-antispamkoppen en -waarden, en acties die het betrouwbaarheidsniveau voor spam van deze berichten instellen op 6:</span><span class="sxs-lookup"><span data-stu-id="957e6-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="957e6-110">`X-Forefront-Antispam-Report: SFV:SPM` (bericht gemarkeerd als spam door spamfilters)</span><span class="sxs-lookup"><span data-stu-id="957e6-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="957e6-111">`X-Forefront-Antispam-Report: SFV:SKS` (bericht gemarkeerd als spam door regels voor de e-mailstroom in EOP vóór spamfilters)</span><span class="sxs-lookup"><span data-stu-id="957e6-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="957e6-112">`X-Forefront-Antispam-Report: SFV:SKB` (Bericht gemarkeerd als spam door spamfilters omdat het e-mailadres of e-maildomein van de afzender in de lijst met geblokkeerde afzenders of de lijst met geblokkeerde domeinen in EOP staat)</span><span class="sxs-lookup"><span data-stu-id="957e6-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="957e6-113">Zie de kopteksten tegen [ongewenste e-mailberichten voor meer informatie over deze kopteksten.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="957e6-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="957e6-114">In dit onderwerp wordt beschreven hoe u deze e-mailstroomregels maakt in het Exchange-beheercentrum (EAC) en in de Exchange-beheershell (Exchange PowerShell) in de on-premises Exchange-organisatie.</span><span class="sxs-lookup"><span data-stu-id="957e6-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="957e6-115">In plaats van de berichten in de map Ongewenste e-mail van de on-premises gebruiker te plaatsen, kunt u antispambeleid in EOP configureren voor het in quarantaine plaatsen van spamberichten in EOP.</span><span class="sxs-lookup"><span data-stu-id="957e6-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="957e6-116">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="957e6-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="957e6-117">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="957e6-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="957e6-118">U moet machtigingen toegewezen krijgen in de on-premises Exchange-omgeving voordat u deze procedures kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="957e6-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="957e6-119">De rol Transportregels, die  standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer** en **Recordbeheer,** moet aan u zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="957e6-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="957e6-120">Zie Leden toevoegen [aan een rollengroep voor meer informatie.](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)</span><span class="sxs-lookup"><span data-stu-id="957e6-120">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="957e6-121">Als en wanneer een bericht wordt bezorgd in de map Ongewenste e-mail in een on-premises Exchange-organisatie, wordt dit bepaald door een combinatie van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="957e6-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="957e6-122">De _parameterwaarde SCLJunkThreshold_ op de cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) in de Exchange-beheershell.</span><span class="sxs-lookup"><span data-stu-id="957e6-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="957e6-123">De standaardwaarde is 4, wat betekent dat een SCL van 5 of hoger het bericht moet bezorgen in de map Ongewenste e-mail van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="957e6-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="957e6-124">De _parameterwaarde SCLJunkThreshold_ op de cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) in de Exchange-beheershell.</span><span class="sxs-lookup"><span data-stu-id="957e6-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="957e6-125">De standaardwaarde is leeg ($null), wat betekent dat de organisatie-instelling wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="957e6-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="957e6-126">Zie voor meer informatie de drempelwaarden voor [het betrouwbaarheidsniveau voor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)spam in Exchange.</span><span class="sxs-lookup"><span data-stu-id="957e6-126">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="957e6-127">Of de regel voor ongewenste e-mail is ingeschakeld in het postvak (de waarde voor de ingeschakelde _parameter_ is $true op de cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) in de Exchange-beheershell).</span><span class="sxs-lookup"><span data-stu-id="957e6-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="957e6-128">Het is de regel voor ongewenste e-mail die het bericht na bezorging daadwerkelijk verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="957e6-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="957e6-129">De regel voor ongewenste e-mail is standaard ingeschakeld voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="957e6-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="957e6-130">Zie [Antispaminstellingen voor Exchange configureren voor postvakken voor meer informatie.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)</span><span class="sxs-lookup"><span data-stu-id="957e6-130">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="957e6-131">Als u het Exchange-beheercentrum wilt openen op een Exchange-server, gaat u naar [het Exchange-beheercentrum in Exchange Server.](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="957e6-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="957e6-132">Zie De Exchange-beheershell openen als u [de Exchange-beheershell wilt openen.](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)</span><span class="sxs-lookup"><span data-stu-id="957e6-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="957e6-133">Zie de volgende onderwerpen voor meer informatie over regels voor de e-mailstroom in on-premises Exchange:</span><span class="sxs-lookup"><span data-stu-id="957e6-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="957e6-134">Regels voor e-mailstroom in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="957e6-134">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="957e6-135">Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="957e6-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="957e6-136">Acties voor e-mailstroomregel in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="957e6-136">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="957e6-137">Het EAC gebruiken om regels voor de e-mailstroom te maken die de SCL van EOP-spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="957e6-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="957e6-138">Ga in het EAC naar **Regels voor e-mailstroom.** \> </span><span class="sxs-lookup"><span data-stu-id="957e6-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="957e6-139">Klik **op** ![ het pictogram Toevoegen en selecteer Een nieuwe regel ](../../media/ITPro-EAC-AddIcon.png) **maken** in de vervolgkeuzebalk die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="957e6-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="957e6-140">Configureer **de volgende** instellingen op de pagina Nieuwe regel die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="957e6-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="957e6-141">**Naam:** voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="957e6-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="957e6-142">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="957e6-142">For example:</span></span>

     - <span data-ttu-id="957e6-143">EOP SFV:SPM naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="957e6-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="957e6-144">EOP SFV:SKS naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="957e6-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="957e6-145">EOP SFV:SKB naar SCL 6</span><span class="sxs-lookup"><span data-stu-id="957e6-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="957e6-146">Klik **op Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="957e6-146">Click **More Options**.</span></span>

   - <span data-ttu-id="957e6-147">**Pas deze regel toe als:** Selecteer **een berichtkop** \> **een van deze woorden bevat.**</span><span class="sxs-lookup"><span data-stu-id="957e6-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="957e6-148">Voer in **de kopTekst invoeren de volgende** stappen uit om woorden in te voeren die worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="957e6-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="957e6-149">Klik **op Tekst invoeren.**</span><span class="sxs-lookup"><span data-stu-id="957e6-149">Click **Enter text**.</span></span> <span data-ttu-id="957e6-150">Voer in het dialoogvenster Naam van **koptekst** opgeven dat wordt weergegeven **X-Forefront-Antispam-Report** in en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="957e6-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="957e6-151">Klik **op Woorden invoeren.**</span><span class="sxs-lookup"><span data-stu-id="957e6-151">Click  **Enter words**.</span></span> <span data-ttu-id="957e6-152">Voer  in het dialoogvenster Woorden of woordgroepen opgeven dat wordt weergegeven een van de waarden voor EOP-spamkoptekst in **(SFV:SPM,** **SFV:SKS** of **SFV:SKB),** klik op pictogram Toevoegen en klik op  ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**</span><span class="sxs-lookup"><span data-stu-id="957e6-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="957e6-153">**Ga als volgt te** werk: **selecteer De berichteigenschappen wijzigen** Stel het \> **betrouwbaarheidsniveau voor ongewenste e-mail in.**</span><span class="sxs-lookup"><span data-stu-id="957e6-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="957e6-154">Selecteer **6** (de standaardwaarde is **5)** in het dialoogvenster **SCL** opgeven dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="957e6-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="957e6-155">Wanneer u klaar bent, klikt u op **Opslaan**</span><span class="sxs-lookup"><span data-stu-id="957e6-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="957e6-156">Herhaal deze stappen voor de resterende waarden voor spam in EOP **(SFV:SPM,** **SFV:SKS** of **SFV:SKB).**</span><span class="sxs-lookup"><span data-stu-id="957e6-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="957e6-157">Gebruik de Exchange-beheershell om regels voor de e-mailstroom te maken die de SCL van EOP-spamberichten instellen</span><span class="sxs-lookup"><span data-stu-id="957e6-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="957e6-158">Gebruik de volgende syntaxis om de drie regels voor de e-mailstroom te maken:</span><span class="sxs-lookup"><span data-stu-id="957e6-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="957e6-159">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="957e6-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="957e6-160">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="957e6-160">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="957e6-161">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="957e6-161">How do you know this worked?</span></span>

<span data-ttu-id="957e6-162">Als u wilt controleren of u de zelfstandige EOP zodanig hebt geconfigureerd dat spam moet worden verzonden naar de map Ongewenste e-mail in een hybride omgeving, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="957e6-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="957e6-163">Ga in het EAC naar Regels voor **e-mailstroom,** selecteer de regel en klik vervolgens op het pictogram Bewerken \> bewerken om de instellingen  ![ te ](../../media/ITPro-EAC-EditIcon.png) controleren.</span><span class="sxs-lookup"><span data-stu-id="957e6-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="957e6-164">Vervang in de Exchange-beheershell door de naam van de regel voor de e-mailstroom en regel de volgende opdracht om \<RuleName\> de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="957e6-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="957e6-165">In een extern e-mailsysteem waarin uitgaande berichten niet op **spam** worden gescand, verzendt u een algemene test voor ongevraagde bulk-e-mail (GTUBE) naar een getroffen geadresseerde en controleert u of het bericht is bezorgd in de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="957e6-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="957e6-166">Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.</span><span class="sxs-lookup"><span data-stu-id="957e6-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="957e6-167">Als u een GTUBE-bericht wilt verzenden, moet u de volgende tekst in de berichttekst van een e-mailbericht opnemen op één regel, zonder spaties of regel-eindes:</span><span class="sxs-lookup"><span data-stu-id="957e6-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
