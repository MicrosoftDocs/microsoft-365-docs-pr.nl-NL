---
title: Ongewenste e-mail en phishing-e-mail melden in de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor ongewenste e-mail, geen ongewenste e-mail en phishing-e-mailrapportage in de webversie van Outlook (Outlook Web App) in Exchange Online, en informatie over het uitschakelen van deze rapportageopties voor gebruikers.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd22e7f08ae420adf2923d4da731494a0f6af3e3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166733"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="841d1-103">Ongewenste e-mail en phishing-e-mail melden in de webversie van Outlook in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="841d1-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="841d1-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="841d1-104">**Applies to**</span></span>
- [<span data-ttu-id="841d1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="841d1-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="841d1-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="841d1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="841d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="841d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="841d1-108">In Microsoft 365-organisaties met postvakken in Exchange Online kunt u de ingebouwde rapportageopties in de webversie van Outlook (voorheen Outlook Web App) gebruiken om fout-positieven (goede e-mail gemarkeerd als spam), fout-negatieven (niet-toegestane e-mail) en phishingberichten in te dienen bij Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="841d1-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="841d1-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="841d1-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="841d1-110">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="841d1-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="841d1-111">Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="841d1-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="841d1-112">Beheerders kunnen de mogelijkheid voor gebruikers om berichten te rapporteren, in- of uitschakelen in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="841d1-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="841d1-113">Zie voor meer informatie het gedeelte over het uitschakelen of inschakelen van rapportage van ongewenste e-mail in de [webversie](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook verder naar dit artikel.</span><span class="sxs-lookup"><span data-stu-id="841d1-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="841d1-114">U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="841d1-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="841d1-115">Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="841d1-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="841d1-116">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over het rapporteren van berichten [naar Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="841d1-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="841d1-117">Spam en phishingberichten rapporteren in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="841d1-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="841d1-118">Voor berichten in het Postvak IN of een andere e-mailmap behalve Ongewenste e-mail gebruikt u een van de volgende methoden om spam en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="841d1-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="841d1-119">Selecteer het bericht, klik op **Ongewenste e-mail** op de werkbalk en selecteer vervolgens **Ongewenste e-mail** of **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="841d1-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Ongewenste e-mail of phishing-e-mail melden via het lint](../../media/owa-report-junk.png)

   - <span data-ttu-id="841d1-121">Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als ongewenste e-mail.**</span><span class="sxs-lookup"><span data-stu-id="841d1-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="841d1-122">Klik in het dialoogvenster dat wordt weergegeven op **Rapport.**</span><span class="sxs-lookup"><span data-stu-id="841d1-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="841d1-123">Als u van gedachten verandert, klikt u **op Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="841d1-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="841d1-124">Ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="841d1-124">Junk</span></span>|<span data-ttu-id="841d1-125">Phishing</span><span class="sxs-lookup"><span data-stu-id="841d1-125">Phishing</span></span>|
   |:---:|:---:|
   |![Dialoogvenster Rapporteren als ongewenste e-mail](../../media/owa-report-as-junk-dialog.png)|![Dialoogvenster Als phishing melden](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="841d1-128">De geselecteerde berichten worden naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="841d1-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="841d1-129">Als u wilt controleren of de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="841d1-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="841d1-130">Niet-spam- en phishingberichten melden vanuit de map Ongewenste e-mail in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="841d1-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="841d1-131">Gebruik in de map Ongewenste e-mail een van de volgende methoden om fout-positieven of phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="841d1-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="841d1-132">Selecteer het bericht, klik op **Geen ongewenste** e-mail op de werkbalk en selecteer vervolgens **Geen ongewenste e-mail** of **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="841d1-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Geen ongewenste e-mail of geen phishing-e-mail vanaf het lint melden](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="841d1-134">Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als niet-ongewenste e-mail.**</span><span class="sxs-lookup"><span data-stu-id="841d1-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="841d1-135">Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.**</span><span class="sxs-lookup"><span data-stu-id="841d1-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="841d1-136">Als u van gedachten verandert, klikt u **op Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="841d1-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="841d1-137">Geen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="841d1-137">Not Junk</span></span>|<span data-ttu-id="841d1-138">Phishing</span><span class="sxs-lookup"><span data-stu-id="841d1-138">Phishing</span></span>|
   |:---:|:---:|
   |![Dialoogvenster Rapporteren als niet-ongewenste e-mail](../../media/owa-report-as-not-junk-dialog.png)|![Dialoogvenster Voor het melden als phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="841d1-141">De geselecteerde berichten worden naar Microsoft verzonden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="841d1-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="841d1-142">Als u wilt controleren of de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="841d1-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="841d1-143">Rapportage van ongewenste e-mail in- of uitschakelen in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="841d1-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="841d1-144">Standaard kunnen gebruikers fout-positieven, fout-negatieven en phishingberichten rapporteren aan Microsoft voor analyse in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="841d1-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="841d1-145">Beheerders kunnen postvakbeleidsregels voor de webversie van Outlook configureren in Exchange Online PowerShell om te voorkomen dat gebruikers fout-positieven en ongewenste e-mail negatieven aan Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="841d1-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="841d1-146">U kunt de mogelijkheid voor gebruikers om phishing-berichten te melden bij Microsoft niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="841d1-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="841d1-147">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="841d1-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="841d1-148">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="841d1-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="841d1-149">U moet machtigingen toegewezen krijgen in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="841d1-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="841d1-150">U hebt met name de rollen **Geadresseerdenbeleid** of  **E-mailontvangers** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer en **Geadresseerdenbeheer.**</span><span class="sxs-lookup"><span data-stu-id="841d1-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="841d1-151">Zie Machtigingen in [Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) en Rollengroepen wijzigen in Exchange Online voor meer informatie over [rollengroepen in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="841d1-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="841d1-152">Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u kunt aangepaste beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="841d1-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="841d1-153">Aangepaste beleidsregels worden vóór het standaardbeleid toegepast op gebruikers met een bereik.</span><span class="sxs-lookup"><span data-stu-id="841d1-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="841d1-154">Zie postvakbeleidsregels in de webversie van Outlook in Exchange Online voor meer informatie over postvakbeleidsregels [in de webversie van Outlook.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="841d1-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="841d1-155">Het uitschakelen van rapportage van ongewenste e-mail betekent niet dat u een bericht in de webversie van Outlook kunt markeren als ongewenste e-mail of als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="841d1-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="841d1-156">Als u een bericht selecteert  in de map Ongewenste e-mail en op Geen ongewenste e-mail klikt, wordt het bericht weer verplaatst \>  naar het Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="841d1-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="841d1-157">Als u een bericht in een  andere e-mailmap selecteert en op Ongewenste e-mail klikt, wordt het bericht toch \>  verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="841d1-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="841d1-158">Wat niet meer beschikbaar is, is de optie om het bericht te rapporteren bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="841d1-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="841d1-159">Exchange Online PowerShell gebruiken om rapportage van ongewenste e-mail in of uit te schakelen in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="841d1-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="841d1-160">Voer de volgende opdracht uit om uw bestaande postvakbeleidsregels voor de webversie van Outlook en de status van het rapporteren van ongewenste e-mail te vinden:</span><span class="sxs-lookup"><span data-stu-id="841d1-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="841d1-161">Gebruik de volgende syntaxis om rapportage van ongewenste e-mail in of uit te schakelen in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="841d1-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="841d1-162">In dit voorbeeld wordt rapportage van ongewenste e-mail in het standaardbeleid uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="841d1-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="841d1-163">In dit voorbeeld wordt rapportage van ongewenste e-mail mogelijk gemaakt in het aangepaste beleid met de naam Contoso-beheerders.</span><span class="sxs-lookup"><span data-stu-id="841d1-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="841d1-164">Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) en [Set-OwaMailboxPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="841d1-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="841d1-165">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="841d1-165">How do you know this worked?</span></span>

<span data-ttu-id="841d1-166">Als u wilt controleren of u rapportage van ongewenste e-mail hebt ingeschakeld of uitgeschakeld in de webversie van Outlook, gebruikt u een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="841d1-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="841d1-167">Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de waarde van de eigenschap **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="841d1-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="841d1-168">Open het postvak van een getroffen gebruiker in de webversie  van Outlook, selecteer een bericht in het Postvak IN, klik op Ongewenste e-mail en controleer of de prompt voor het rapporteren van het bericht aan Microsoft wel of niet \>  wordt weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="841d1-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="841d1-169">Open het postvak van een getroffen gebruiker in de webversie van  Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op Ongewenste e-mail en controleer of de prompt voor het rapporteren van het bericht aan Microsoft wel of niet \>  wordt weergegeven.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="841d1-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="841d1-170"><sup>\*</sup> Gebruikers kunnen de prompt voor het rapporteren van het bericht verbergen terwijl ze het bericht nog steeds rapporteren.</span><span class="sxs-lookup"><span data-stu-id="841d1-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="841d1-171">Deze instelling controleren in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="841d1-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="841d1-172">Klik **op het** pictogram Instellingen voor de ![ webinstellingen van Outlook Alle ](../../media/owa-settings-icon.png) \> **Outlook-instellingen voor** ongewenste \> **e-mail weergeven.**</span><span class="sxs-lookup"><span data-stu-id="841d1-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="841d1-173">Controleer in **de sectie** Rapportage de waarde: Mij vragen voordat u een **rapport verstuurt.**</span><span class="sxs-lookup"><span data-stu-id="841d1-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Instellingen voor rapportage van ongewenste e-mail in Outlook op het web](../../media/owa-junk-email-reporting-options.png)
