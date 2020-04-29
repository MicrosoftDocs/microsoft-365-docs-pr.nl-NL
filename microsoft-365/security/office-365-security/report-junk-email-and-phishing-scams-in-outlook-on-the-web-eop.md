---
title: 'Ongewenste e-mail en phishing-scams melden in de webversie van Outlook '
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
description: Microsoft 365-gebruikers met Exchange Online-postvakken kunnen Outlook op internet (Outlook Web App) gebruiken om spam-, niet-spam- en phishingberichten naar Microsoft te verzenden voor analyse.
ms.openlocfilehash: 9fc17abafe219a450e0fb6e45438211ea03fb337
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921478"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="8c4f7-103">Ongewenste en phishing-e-mail melden in de webversie van Outlook in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c4f7-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="8c4f7-104">Als u een Microsoft 365-klant bent met Exchange Online-postvakken, u de ingebouwde rapportageopties in Outlook op de web (voorheen Outlook Web App) gebruiken om false positives (goede e-mail gemarkeerd als spam), valse negatieven (slechte e-mail toegestaan) en phishing-berichten in te dienen bij Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="8c4f7-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8c4f7-105">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8c4f7-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8c4f7-106">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="8c4f7-107">Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="8c4f7-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="8c4f7-108">Beheerders kunnen de mogelijkheid voor gebruikers om berichten aan Microsoft te melden in de webversie van Outlook uitschakelen of inschakelen.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="8c4f7-109">Zie de [rapportage over ongewenste e-mail in de websectie](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook later in dit onderwerp voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="8c4f7-110">U configureren dat gerapporteerde berichten worden gekopieerd of doorgestuurd naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="8c4f7-111">Zie [Een postvak opgeven voor het indienen van spam- en phishingberichten in Office 365 voor](user-submission.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="8c4f7-112">Zie [Berichten en bestanden rapporteren aan Microsoft in Office 365](report-junk-email-messages-to-microsoft.md)voor meer informatie over het rapporteren van berichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="8c4f7-113">Spam- en phishingberichten melden in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="8c4f7-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="8c4f7-114">Voor berichten in het Postvak IN of een andere e-mailmap, met uitzondering van ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="8c4f7-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="8c4f7-115">Selecteer het bericht, klik op **Ongewenste e-mail** op de werkbalk en selecteer **Ongewenste** **of phishing.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/owa-report-junk.png)

   - <span data-ttu-id="8c4f7-117">Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als ongewenste e-mail.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="8c4f7-118">Klik in het dialoogvenster dat wordt weergegeven op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="8c4f7-119">Als u van gedachten verandert, klikt u op **Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-119">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport als pictogram ongewenste e-mail](../../media/owa-report-as-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="8c4f7-122">De geselecteerde berichten worden naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-122">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="8c4f7-123">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-123">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="8c4f7-124">Niet-spam- en phishingberichten melden vanuit de map Ongewenste e-mail in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="8c4f7-124">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="8c4f7-125">Gebruik in de map Ongewenste e-mail een van de volgende methoden om valse positieven of phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="8c4f7-125">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="8c4f7-126">Selecteer het bericht, klik op **Geen ongewenstee informatie** op de werkbalk en selecteer **Geen ongewenste e-mail** of **phishing**.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-126">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="8c4f7-128">Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als geen ongewenste e-mail.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-128">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="8c4f7-129">Lees in het dialoogvenster dat wordt weergegeven de informatie en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-129">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="8c4f7-130">Als u van gedachten verandert, klikt u op **Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-130">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport als niet-ongewenste dialoogvenster](../../media/owa-report-as-not-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="8c4f7-133">De geselecteerde berichten worden naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-133">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="8c4f7-134">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-134">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="8c4f7-135">Meldingen van ongewenste e-mail uitschakelen of inschakelen in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="8c4f7-135">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="8c4f7-136">Standaard kunnen gebruikers spamfout-positieven, valse negatieven en phishingberichten melden aan Microsoft voor analyse in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-136">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="8c4f7-137">Beheerders kunnen Outlook configureren op het beleid voor webpostvakinen in Exchange Online PowerShell om te voorkomen dat gebruikers valse positieven en spamnegatieven melden bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-137">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="8c4f7-138">U de mogelijkheid voor gebruikers om phishingberichten aan Microsoft te melden niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-138">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8c4f7-139">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8c4f7-139">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8c4f7-140">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-140">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="8c4f7-141">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-141">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="8c4f7-142">U hebt met name de rollen **Geadresseerden** of **Geadresseerden** nodig in Exchange Online, die standaard zijn toegewezen aan de rolgroepen **Organisatiebeheer** en **Geadresseerdbeheer.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-142">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="8c4f7-143">Zie [Rolgroepen wijzigen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)voor meer informatie over rolgroepen in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="8c4f7-143">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="8c4f7-144">Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u aangepaste beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-144">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="8c4f7-145">Aangepaste beleidsregels worden toegepast op gebruikers met scopen vóór het standaardbeleid.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-145">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="8c4f7-146">Zie [Outlook voor het webpostvakbeleid in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)voor meer informatie over het beleid voor webpostvak.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-146">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="8c4f7-147">Als u ongewenste e-mailrapportage uitschakelt, wordt de mogelijkheid om een bericht te markeren niet als ongewenste e-mail verwijderd of niet als ongewenste e-mail in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-147">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="8c4f7-148">Als u een bericht selecteert in de map Ongewenste e-mail en op **Niet ongewenstee berichten** \> **klikt,** wordt het bericht nog steeds teruggezet naar het Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-148">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="8c4f7-149">Als u een bericht selecteert in een andere e-mailmap en op **Ongewenste e-mail** \> **klikt,** wordt het bericht nog steeds verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-149">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="8c4f7-150">Wat niet meer beschikbaar is, is de optie om het bericht aan Microsoft te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-150">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="8c4f7-151">Exchange Online PowerShell gebruiken om meldingen van ongewenste e-mail uit te schakelen of in te schakelen in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="8c4f7-151">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="8c4f7-152">Voer de volgende opdracht uit om uw bestaande Outlook voor het webpostvakbeleid en de status van ongewenste e-mailrapportage te vinden:</span><span class="sxs-lookup"><span data-stu-id="8c4f7-152">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="8c4f7-153">Als u de rapportage met ongewenste e-mail wilt uitschakelen of inschakelen in de webversie van Outlook, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="8c4f7-153">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="8c4f7-154">In dit voorbeeld wordt melding van ongewenste e-mail in het standaardbeleid uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-154">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="8c4f7-155">In dit voorbeeld wordt melding van ongewenste e-mail mogelijk gemaakt in het aangepaste beleid met de naam Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-155">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="8c4f7-156">Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) en [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-156">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8c4f7-157">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="8c4f7-157">How do you know this worked?</span></span>

<span data-ttu-id="8c4f7-158">Gebruik een van de volgende stappen om te controleren of u de rapportage over ongewenste e-mail in Outlook hebt ingeschakeld of uitgeschakeld in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="8c4f7-158">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="8c4f7-159">Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de eigenschapswaarde **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-159">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="8c4f7-160">Open het postvak van een betrokken gebruiker in de webversie van Outlook, selecteer een bericht in het Postvak IN, klik op **Ongewenste** \> **e-mail** en controleer of de prompt om het bericht aan Microsoft te melden wel of niet wordt weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8c4f7-160">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="8c4f7-161">Open het postvak van een betrokken gebruiker in de webversie van Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op **Ongewenste** \> **e-mail** en controleer of het bericht aan Microsoft wordt gemeld of niet wordt weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8c4f7-161">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="8c4f7-162"><sup>\*</sup>Gebruikers kunnen de prompt verbergen om het bericht te rapporteren terwijl ze het bericht nog steeds rapporteren.</span><span class="sxs-lookup"><span data-stu-id="8c4f7-162"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="8c4f7-163">Ga als volgt te werk om deze instelling in de webversie van Outlook te controleren:</span><span class="sxs-lookup"><span data-stu-id="8c4f7-163">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="8c4f7-164">Klik op **Instellingen** ![Outlook](../../media/owa-settings-icon.png) \> op het pictogram Webinstellingen Bekijk alle **ongewenste e-mail van** **Outlook-instellingen** \> .</span><span class="sxs-lookup"><span data-stu-id="8c4f7-164">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="8c4f7-165">Controleer in de sectie **Rapportage** de waarde: **Vraag het mij voordat u een rapport verzendt.**</span><span class="sxs-lookup"><span data-stu-id="8c4f7-165">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Instellingen voor meldingen van ongewenste e-mail in Outlook op de web](../../media/owa-junk-email-reporting-options.png)
