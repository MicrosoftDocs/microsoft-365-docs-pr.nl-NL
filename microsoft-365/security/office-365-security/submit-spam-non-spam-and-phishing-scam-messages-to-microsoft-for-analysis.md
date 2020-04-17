---
title: Berichten handmatig verzenden naar Microsoft voor analyse
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'U en uw gebruikers kunnen valse negatieve en fout-positieve spamberichten naar Microsoft sturen voor analyse. '
ms.openlocfilehash: 77807f710743d98dc2e1564f804b6a67add67def
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529047"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="0b49d-103">Berichten handmatig verzenden naar Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="0b49d-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="0b49d-104">Als u een beheerder bent in een Office 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="0b49d-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="0b49d-105">Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="0b49d-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="0b49d-106">Het kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten ontvangen in hun Postvak IN, of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="0b49d-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="0b49d-107">We verfijnen onze spamfilters voortdurend om nauwkeuriger te zijn.</span><span class="sxs-lookup"><span data-stu-id="0b49d-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="0b49d-108">U en uw gebruikers kunnen dit proces helpen door false positives (goede e-mail gemarkeerd als slecht), valse negatieven (slechte e-mail toegestaan) en phishing-berichten bij Microsoft in te dienen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="0b49d-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="0b49d-109">Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle verzoeken om analyse beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="0b49d-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="0b49d-110">Valse negatieven verzenden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="0b49d-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="0b49d-111">In plaats van de volgende procedures te gebruiken om valse negatieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook (voorheen Outlook Web App) de invoegtoepassing Berichtrapport voor Microsoft Outlook gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0b49d-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="0b49d-112">Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.</span><span class="sxs-lookup"><span data-stu-id="0b49d-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="0b49d-113">Als u een bericht ontvangt dat door spamfiltering is verzonden en dat als spam of phishing had moeten worden geïdentificeerd, u het bericht naar gelang van het geval indienen bij de microsoft spamanalyse- en Microsoft Phishing-analyseteams.</span><span class="sxs-lookup"><span data-stu-id="0b49d-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="0b49d-114">De analisten zullen het bericht bekijken en toevoegen aan de servicebrede filters als het voldoet aan de classificatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="0b49d-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="0b49d-115">Maak een nieuw, leeg e-mailbericht met een van de volgende ontvangers:</span><span class="sxs-lookup"><span data-stu-id="0b49d-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="0b49d-116">**Junk**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="0b49d-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="0b49d-117">**Phishing**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="0b49d-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="0b49d-118">Sleep en drop de ongewenste of phishing-bericht in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="0b49d-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="0b49d-119">Dit zal de junk of phishing-bericht op te slaan als een bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="0b49d-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="0b49d-120">Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).</span><span class="sxs-lookup"><span data-stu-id="0b49d-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="0b49d-121">U meerdere berichten toevoegen in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="0b49d-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="0b49d-122">Zorg ervoor dat alle berichten hetzelfde type zijn: phishing-scamberichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="0b49d-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="0b49d-123">Laat het lichaam van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="0b49d-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="0b49d-124">Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="0b49d-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="0b49d-125">Klik op **Verzenden**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0b49d-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="0b49d-126">Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die verkeerd worden geïdentificeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="0b49d-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="0b49d-127">Zie Lijsten [met geblokkeerde afzenders maken in Office 365](create-block-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b49d-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="0b49d-128">Valse positieven verzenden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="0b49d-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="0b49d-129">In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook de invoegtoepassing Rapportbericht voor Microsoft Outlook gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0b49d-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="0b49d-130">Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.</span><span class="sxs-lookup"><span data-stu-id="0b49d-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="0b49d-131">Als een bericht ten onrechte is geïdentificeerd als spam, u het bericht indienen bij het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="0b49d-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="0b49d-132">De analisten evalueren het bericht en (afhankelijk van de resultaten van de analyse) kunnen de servicebrede filters worden aangepast om het bericht door te laten gaan.</span><span class="sxs-lookup"><span data-stu-id="0b49d-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="0b49d-133">Maak een nieuw, leeg `not_junk@office365.microsoft.com` e-mailbericht met als ontvanger:</span><span class="sxs-lookup"><span data-stu-id="0b49d-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="0b49d-134">Sleep en laat het verkeerd geïdentificeerde bericht in het nieuwe bericht vallen.</span><span class="sxs-lookup"><span data-stu-id="0b49d-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="0b49d-135">Hiermee wordt het verkeerd geïdentificeerde bericht opgeslagen als bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="0b49d-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="0b49d-136">Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).</span><span class="sxs-lookup"><span data-stu-id="0b49d-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="0b49d-137">U meerdere berichten toevoegen in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="0b49d-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="0b49d-138">Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="0b49d-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="0b49d-139">Laat het lichaam van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="0b49d-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="0b49d-140">Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="0b49d-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="0b49d-141">Klik op **Verzenden**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0b49d-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="0b49d-142">Beheerders hebben verschillende manieren om specifieke berichten toe te staan spamfilters over te slaan.</span><span class="sxs-lookup"><span data-stu-id="0b49d-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="0b49d-143">Zie Lijsten [met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b49d-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="0b49d-144">Een e-mailstroomregel maken om kopieën te ontvangen van berichten die aan Microsoft worden gerapporteerd</span><span class="sxs-lookup"><span data-stu-id="0b49d-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="0b49d-145">U een regel voor e-mailstroom (ook wel een transportregel genoemd) maken die zoekt naar e-mailberichten die aan Microsoft worden gerapporteerd met behulp van de methoden die in dit onderwerp zijn beschreven, en u BCC-ontvangers configureren om kopieën van deze gerapporteerde berichten te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0b49d-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="0b49d-146">U de regel voor e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Office 365-klanten. Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).</span><span class="sxs-lookup"><span data-stu-id="0b49d-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b49d-147">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0b49d-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b49d-148">U moet machtigingen in Exchange Online krijgen toegewezen voordat u deze procedures uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0b49d-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="0b49d-149">U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.**</span><span class="sxs-lookup"><span data-stu-id="0b49d-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="0b49d-150">Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="0b49d-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="0b49d-151">Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)als u de EAC in Exchange Online wilt openen.</span><span class="sxs-lookup"><span data-stu-id="0b49d-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="0b49d-152">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b49d-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0b49d-153">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b49d-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b49d-154">Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="0b49d-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="0b49d-155">Regels voor e-mailstroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0b49d-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="0b49d-156">Voorwaarden en uitzonderingen voor e-mailstroomregels (predicaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0b49d-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="0b49d-157">Acties voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0b49d-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="0b49d-158">De EAC gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="0b49d-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="0b49d-159">Ga in de EAC naar **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="0b49d-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="0b49d-160">Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="0b49d-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="0b49d-161">Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0b49d-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="0b49d-162">**Naam:** Voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="0b49d-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="0b49d-163">Bijvoorbeeld, BCC Berichten Gerapporteerd aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b49d-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="0b49d-164">Klik **op Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="0b49d-164">Click **More Options**.</span></span>

   - <span data-ttu-id="0b49d-165">**Deze regel toepassen als**: **Selecteer Het geadresseerdeadres** \> **bevat een van deze woorden:** Voer in het dialoogvenster](../../media/ITPro-EAC-AddIcon.png)Woorden of zinnen **opgeven** dat wordt weergegeven een van de volgende waarden in, klik op Pictogram **toevoegen** ![en herhaal totdat u alle waarden hebt ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="0b49d-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="0b49d-166">Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken .</span><span class="sxs-lookup"><span data-stu-id="0b49d-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="0b49d-167">Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="0b49d-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="0b49d-168">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0b49d-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="0b49d-169">**Ga als volgt**te werk : Selecteer **Geadresseerden** \> toevoegen **aan het vak BCC**.</span><span class="sxs-lookup"><span data-stu-id="0b49d-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="0b49d-170">Zoek en selecteer in het dialoogvenster dat wordt weergegeven de geadresseerden die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0b49d-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="0b49d-171">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0b49d-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="0b49d-172">U extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="0b49d-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="0b49d-173">We raden u aan de regel te testen voordat u deze afdwingt.</span><span class="sxs-lookup"><span data-stu-id="0b49d-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="0b49d-174">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0b49d-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="0b49d-175">PowerShell gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="0b49d-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="0b49d-176">In dit voorbeeld wordt een nieuwe regel voor e-mailstroom gemaakt met de naam BCC-berichten die aan Microsoft worden gerapporteerd en die wordt gerapporteerd met behulp van de methoden die in dit onderwerp zijn beschreven, en worden de gebruikers laura@contoso.com en julia@contoso.com toegevoegd als BCC-ontvangers.</span><span class="sxs-lookup"><span data-stu-id="0b49d-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="0b49d-177">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="0b49d-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0b49d-178">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="0b49d-178">How do you know this worked?</span></span>

<span data-ttu-id="0b49d-179">Ga een van de volgende stappen uit om te controleren of u een e-mailstroomregels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen:</span><span class="sxs-lookup"><span data-stu-id="0b49d-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="0b49d-180">Ga in de EAC naar **EAC-regels** \> **Rules** \> en selecteer](../../media/ITPro-EAC-EditIcon.png)de regel \> klik op Pictogram Bewerken **bewerken** ![en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="0b49d-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="0b49d-181">Voer in PowerShell de volgende opdracht uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="0b49d-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="0b49d-182">Stuur een testbericht naar een van de rapportage-e-mailadressen en verifieer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="0b49d-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
