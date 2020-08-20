---
title: Ongewenste e-mail en phishingberichten rapporteren in de webversie van Outlook
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie vinden over de ingebouwde opties voor ongewenste e-mail, ongewenste e-mail en het rapporteren van e-mailberichten in de webversie van Outlook (Outlook Web app) in Exchange Online, en hoe u deze rapportageopties voor gebruikers uitschakelt.
ms.openlocfilehash: a364afed9bb7e61d5f34ffc0206ede1c5155db65
ms.sourcegitcommit: c692bdc186fb29499816e8bb2addcddef34d23d3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818331"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="f8f69-103">Ongewenste e-mail en malafide e-mailberichten in de webversie van Outlook melden in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f8f69-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="f8f69-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunt u gebruikmaken van de ingebouwde rapportopties in de webversie van Outlook (voorheen Outlook Web app) voor het verzenden van foutberichten (goede e-mailberichten die als spam zijn gemarkeerd), onjuiste negatieven (onjuiste e-mail toegestaan) en phishingberichten voor Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f8f69-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8f69-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f8f69-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f8f69-106">Als u een beheerder bent van een organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="f8f69-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f8f69-107">Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="f8f69-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="f8f69-108">Beheerders kunnen gebruikers de mogelijkheid bieden om berichten te rapporteren aan Microsoft in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="f8f69-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="f8f69-109">Zie voor meer informatie de sectie het [melden van ongewenste e-mail in Outlook op het web in-of uitschakelen](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) verderop in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="f8f69-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="f8f69-110">U kunt gerapporteerde berichten configureren voor kopiëren of omleiden naar een door u opgegeven postvak.</span><span class="sxs-lookup"><span data-stu-id="f8f69-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f8f69-111">Zie voor meer informatie [een postvak opgeven voor het overzetten van gebruikers van spam en phishing-berichten in Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="f8f69-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="f8f69-112">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over het rapporteren van berichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8f69-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="f8f69-113">Spam en phishing-berichten rapporteren in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f8f69-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="f8f69-114">Voor berichten in het postvak in of een andere e-mailmap met uitzondering van ongewenste E-mail, gebruikt u een van de volgende methoden om spamberichten en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="f8f69-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="f8f69-115">Selecteert u het bericht, klikt u op **ongewenste e-mail** op de werkbalk en selecteert u vervolgens **ongewenste e-mail** of **phishing**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Ongewenste e-mail of malafide e-mail melden via het lint](../../media/owa-report-junk.png)

   - <span data-ttu-id="f8f69-117">Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer vervolgens **markeren als ongewenst**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="f8f69-118">Klik in het dialoogvenster dat wordt weergegeven op **rapport**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="f8f69-119">Als u van gedachten verandert, klikt u op **niet melden**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="f8f69-120">Ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="f8f69-120">Junk</span></span>|<span data-ttu-id="f8f69-121">Phishing</span><span class="sxs-lookup"><span data-stu-id="f8f69-121">Phishing</span></span>|
   |:---:|:---:|
   |![Melden als ongewenst dialoogvenster](../../media/owa-report-as-junk-dialog.png)|![Melden als phishing-dialoogvenster](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="f8f69-124">De geselecteerde berichten worden naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f8f69-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="f8f69-125">Als u wilt controleren of de berichten zijn verzonden, opent u de map **verzonden items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f8f69-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="f8f69-126">Niet-spamberichten en phishingberichten melden in de map Ongewenste E-mail in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f8f69-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="f8f69-127">Gebruik in de map Ongewenste E-mail een van de volgende methoden om spam in te stellen:</span><span class="sxs-lookup"><span data-stu-id="f8f69-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="f8f69-128">Selecteer het bericht, klik op **geen ongewenste e-mail** op de werkbalk en selecteer **geen ongewenste e-mail** of **phishing**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Ongewenste e-mail of malafide e-mail melden via het lint](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="f8f69-130">Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **markeren als niet-ongewenste e-mail**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="f8f69-131">In het dialoogvenster dat wordt weergegeven, leest u de informatie en klikt u op **rapport**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f8f69-132">Als u van gedachten verandert, klikt u op **niet melden**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="f8f69-133">Geen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="f8f69-133">Not Junk</span></span>|<span data-ttu-id="f8f69-134">Phishing</span><span class="sxs-lookup"><span data-stu-id="f8f69-134">Phishing</span></span>|
   |:---:|:---:|
   |![Dialoogvenster als niet-ongewenste e-mail rapporteren](../../media/owa-report-as-not-junk-dialog.png)|![Melden als phishing-dialoogvenster](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="f8f69-137">De geselecteerde berichten worden naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f8f69-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="f8f69-138">Als u wilt controleren of de berichten zijn verzonden, opent u de map **verzonden items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f8f69-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="f8f69-139">Rapportage van ongewenste e-mail in-of uitschakelen in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f8f69-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="f8f69-140">Standaard kunnen gebruikers spam in de webversie van Outlook melden, geen valse negatieven en phishingberichten met Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f8f69-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="f8f69-141">Beheerders kunnen de beleidsregels voor het postvak van Outlook configureren in Exchange Online PowerShell om te voorkomen dat gebruikers spam fout-en spamberichten van Microsoft rapporteren.</span><span class="sxs-lookup"><span data-stu-id="f8f69-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="f8f69-142">U kunt de mogelijkheid van gebruikers om phishingberichten te rapporteren niet uitschakelen voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8f69-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8f69-143">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f8f69-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f8f69-144">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8f69-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f8f69-145">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="f8f69-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f8f69-146">Specifiek hebt u de rollen voor het **beleid voor geadresseerden** of **e-mail geadresseerden** nodig in Exchange Online, die standaard zijn toegewezen aan de rollen groepen **Organisatiebeheer** en **geadresseerden beheren** .</span><span class="sxs-lookup"><span data-stu-id="f8f69-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="f8f69-147">Zie [rollen groepen wijzigen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)voor meer informatie over rollen groepen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f8f69-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="f8f69-148">Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-standaard, maar u kunt aangepaste beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="f8f69-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="f8f69-149">Aangepaste beleidsregels worden toegepast op gebruikers met een bereik vóór het standaardbeleid.</span><span class="sxs-lookup"><span data-stu-id="f8f69-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="f8f69-150">Zie voor meer informatie over de beleidsregels van de webversie van Outlook voor informatie over de beleidsregels voor het Postvak [in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="f8f69-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="f8f69-151">Als u het rapporteren van ongewenste e-mail uitschakelt, wordt de mogelijkheid om een bericht niet te markeren als ongewenst of niet-ongewenste e-mail in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="f8f69-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="f8f69-152">Als u een bericht in de map Ongewenste e-mail selecteert en op **geen ongewenste e-mail** klikt, wordt \> **Not junk** het bericht nog steeds naar het postvak in verplaatst.</span><span class="sxs-lookup"><span data-stu-id="f8f69-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="f8f69-153">Als u een bericht in een andere e-mailmap selecteert en op **ongewenste** e-mail klikt, wordt \> **Junk** het bericht nog steeds verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="f8f69-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="f8f69-154">Wat niet langer beschikbaar is, is de mogelijkheid om het bericht aan Microsoft te melden.</span><span class="sxs-lookup"><span data-stu-id="f8f69-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="f8f69-155">PowerShell van Exchange Online gebruiken voor het in-of uitschakelen van de rapportage van ongewenste e-mail in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f8f69-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="f8f69-156">Voer de volgende opdracht uit om uw bestaande postvak beleidsregels en de status van rapporten voor ongewenste e-mail te zoeken in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="f8f69-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="f8f69-157">Gebruik de volgende syntaxis om het rapporteren van ongewenste e-mail in de webversie van Outlook uit of in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="f8f69-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="f8f69-158">In dit voorbeeld wordt rapportage van ongewenste e-mail in het standaardbeleid uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f8f69-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="f8f69-159">In dit voorbeeld wordt het rapporteren van ongewenste e-mail ingeschakeld in het aangepaste beleid genaamd contoso managers.</span><span class="sxs-lookup"><span data-stu-id="f8f69-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="f8f69-160">Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) en [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="f8f69-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f8f69-161">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="f8f69-161">How do you know this worked?</span></span>

<span data-ttu-id="f8f69-162">Ga op een van de volgende manieren te werk om te controleren of u de rapportage voor ongewenste e-mail hebt ingeschakeld of uitgeschakeld in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="f8f69-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="f8f69-163">In Exchange Online PowerShell voert u de volgende opdracht uit en controleert u de waarde van de eigenschap **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="f8f69-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="f8f69-164">Het postvak van een gebruiker openen in de webversie van Outlook Selecteer een bericht in het postvak in, klik op **ongewenste** \> **e-mail** en controleer of het bericht aan Microsoft wordt gemeld of niet wordt weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8f69-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="f8f69-165">Open het postvak van een gebruiker in de webversie van Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op **ongewenste** \> **e-mail** en controleer of het bericht aan Microsoft is of niet wordt weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8f69-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="f8f69-166"><sup>\*</sup> Gebruikers kunnen de prompt voor het melden van het bericht verbergen en het bericht nog steeds rapporteren.</span><span class="sxs-lookup"><span data-stu-id="f8f69-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="f8f69-167">Ga als volgt te werk om deze instelling te controleren in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="f8f69-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="f8f69-168">Klik op **instellingen** ![ in Outlook op het pictogram webversies om ](../../media/owa-settings-icon.png) \> **alle Outlook** \> **-instellingen ongewenste e-mail**weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f8f69-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="f8f69-169">Controleer in de sectie **rapportage** de waarde: **vragen voordat u een rapport verzendt**.</span><span class="sxs-lookup"><span data-stu-id="f8f69-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Rapportage-instellingen voor ongewenste E-mail in de webversie van Outlook](../../media/owa-junk-email-reporting-options.png)
