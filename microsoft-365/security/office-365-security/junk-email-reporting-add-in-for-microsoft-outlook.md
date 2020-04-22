---
title: De invoegtoepassing Voor het melden van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Meer informatie over het installeren en gebruiken van de invoegtoepassing Microsoft Ongewenste E-mailrapportage om spam-, niet-spam- en phishingberichten aan Microsoft te melden.
ms.openlocfilehash: be087a15071114b2d1ec564cbb118dcd85e32429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638498"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="68c31-103">De invoegtoepassing Voor melding van ongewenste e-mail rapportage voor Microsoft Outlook installeren en gebruiken in Office 365</span><span class="sxs-lookup"><span data-stu-id="68c31-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="68c31-104">Als u momenteel de invoegtoepassing Ongewenste e-mailrapportage niet gebruikt, raden we in plaats daarvan de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md) aan.</span><span class="sxs-lookup"><span data-stu-id="68c31-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="68c31-105">Met de invoegtoepassing Ongewenste e-mailrapportage voor Microsoft Outlook kunnen gebruikers valse positieven (goede e-mail gemarkeerd als spam), valse negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="68c31-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="68c31-106">Als uw organisatie Geen EOP gebruikt, heeft het indienen van uw ongewenste e-mailrapport geen invloed op uw spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="68c31-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="68c31-107">In dit onderwerp wordt uitgelegd hoe u de invoegtoepassing Ongewenste e-mailrapportage installeert en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="68c31-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="68c31-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="68c31-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="68c31-109">Zie de invoegtoepassing Voor het rapporteren van [ongewenste e-mail](#install-the-junk-email-reporting-add-in) later in dit onderwerp als u de invoegtoepassing Voor ongewenste e-mailrapportage wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="68c31-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="68c31-110">De invoegtoepassing Voor ongewenste e-mailrapportage werkt met de volgende versies van Outlook:</span><span class="sxs-lookup"><span data-stu-id="68c31-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="68c31-111">Outlook 2013 of hoger</span><span class="sxs-lookup"><span data-stu-id="68c31-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="68c31-112">Outlook opgenomen in Microsoft 365 Apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="68c31-112">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="68c31-113">Zie [Berichten en bestanden rapporteren aan Microsoft in Office 365](report-junk-email-messages-to-microsoft.md)voor meer informatie over het rapporteren van berichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68c31-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="68c31-114">De invoegtoepassing Ongewenste e-mailrapportage gebruiken om spam- en phishingberichten te melden</span><span class="sxs-lookup"><span data-stu-id="68c31-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="68c31-115">Voor berichten in het Postvak IN of een andere e-mailmap, met uitzondering van Ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="68c31-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="68c31-116">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="68c31-116">Select the message or open the message.</span></span> <span data-ttu-id="68c31-117">Klik op het tabblad **Start** of **Bericht** op het lint op **Ongewenste e-mail**en selecteer **Vervolgens Rapporteren als ongewenste e-mail** of **Rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="68c31-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="68c31-119">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail**en selecteer **Vervolgens Rapporteren als ongewenste e-mail** of Rapport als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="68c31-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste of phishing-e-mail melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="68c31-121">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als ongewenste e-mail** of **Rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="68c31-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Meerdere ongewenste of phishing-e-mailberichten melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="68c31-123">Lees in het dialoogvenster dat wordt weergegeven de informatie en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="68c31-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="68c31-124">Als u van gedachten verandert, klikt u op **Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="68c31-124">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport als pictogram ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="68c31-127">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="68c31-127">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder.</span></span> <span data-ttu-id="68c31-128">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="68c31-128">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="68c31-129">De invoegtoepassing Ongewenste e-mailrapportage gebruiken om niet-spam- en phishingberichten te melden vanuit de map Ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="68c31-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="68c31-130">Gebruik in de map Ongewenste e-mail een van de volgende methoden om valse positieven of phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="68c31-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="68c31-131">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="68c31-131">Select the message or open the message.</span></span> <span data-ttu-id="68c31-132">Klik op het tabblad **Start** of **Bericht** op het lint op **Geen ongewenstee informatie**en selecteer Vervolgens Rapporteren als Niet ongewenste **e-mail** of **Rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="68c31-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Geen ongewenste e-mail of phishing melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="68c31-134">Klik met de rechtermuisknop op het bericht, klik op **Ongewenste e-mail**en selecteer **Rapporteren als Niet ongewenste e-mail** of Rapport als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="68c31-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Geen ongewenste e-mail of phishing melden vanaf de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="68c31-136">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als Niet ongewenste e-mail** of Meld als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="68c31-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Meerdere niet-ongewenste of phishing-e-mailberichten melden met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="68c31-138">Lees in het dialoogvenster dat wordt weergegeven de informatie en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="68c31-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="68c31-139">Als u van gedachten verandert, klikt u op **Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="68c31-139">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport als niet-ongewenste dialoogvenster](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="68c31-142">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="68c31-142">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder.</span></span> <span data-ttu-id="68c31-143">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="68c31-143">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="68c31-144">De invoegtoepassing Voor het melden van ongewenste e-mail installeren</span><span class="sxs-lookup"><span data-stu-id="68c31-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="68c31-145">U moet beheerdersbevoegdheden hebben op de computer waar u de invoegtoepassing installeert.</span><span class="sxs-lookup"><span data-stu-id="68c31-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="68c31-146">Ga <https://www.microsoft.com/download/details.aspx?id=18275> naar en download het juiste .msi-bestand voor uw versie van Office naar een locatie die gemakkelijk te vinden is:</span><span class="sxs-lookup"><span data-stu-id="68c31-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="68c31-147">**32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="68c31-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="68c31-148">**64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="68c31-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="68c31-149">Voor Outlook 2013 of hoger is de enige voorwaarde het Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="68c31-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="68c31-150">In Windows 10 installeert u het .NET Framework 2.0 niet vanaf een download.</span><span class="sxs-lookup"><span data-stu-id="68c31-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="68c31-151">De invoegtoepassing voor ongewenste e-mailrapportage installeren met de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="68c31-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="68c31-152">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="68c31-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="68c31-153">Controleer in Windows 10 of het .NET Framework 2.0 is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="68c31-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="68c31-154">Zie Het [.NET Framework 3.5 inschakelen in het Configuratiescherm](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)voor instructies .</span><span class="sxs-lookup"><span data-stu-id="68c31-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="68c31-155">Zoek het .msi-bestand dat je hebt gedownload en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="68c31-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="68c31-156">Klik op de pagina **Invoegtoepassing Installatie van ongewenste e-mail van Microsoft** op de pagina Welkom bij Microsoft Ongewenste E-mailrapportage op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="68c31-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="68c31-157">Bekijk de licentieovereenkomst, klik op **Ik accepteer de voorwaarden in de licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="68c31-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="68c31-158">Wanneer de wizard is voltooid, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="68c31-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="68c31-159">Outlook starten.</span><span class="sxs-lookup"><span data-stu-id="68c31-159">Start Outlook.</span></span>

<span data-ttu-id="68c31-160">Zoek naar de knop **Ongewenstee inhoud** op het outlook-lint.</span><span class="sxs-lookup"><span data-stu-id="68c31-160">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="68c31-161">U nu ongewenste e-mailberichten aan Microsoft rapporteren door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste e-mail** melden te klikken.</span><span class="sxs-lookup"><span data-stu-id="68c31-161">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="68c31-162">Kies de pijl-omlaag naast **Ongewenstee opties** voor meer opties, zoals **Melden als Phishing** als u phishing-scam-e-mails aan Microsoft wilt melden.</span><span class="sxs-lookup"><span data-stu-id="68c31-162">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="68c31-163">In uw map met ongewenste e-mail u ook verwijderen, **Geen ongewenste e-mail** melden als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="68c31-163">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="68c31-164">De invoegtoepassing voor ongewenste e-mailrapportage installeren met de stille modus</span><span class="sxs-lookup"><span data-stu-id="68c31-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="68c31-165">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="68c31-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="68c31-166">Installeer in Windows 10 het .NET Framework 2.0 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="68c31-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="68c31-167">Als u de invoegtoepassing zonder gebruikersinteractie wilt installeren, opent u een opdrachtprompt en gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="68c31-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="68c31-168">`MaxMessageSelection`hiermee geeft u het maximumaantal berichten op dat u voor één inzending selecteren.</span><span class="sxs-lookup"><span data-stu-id="68c31-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="68c31-169">Geldige waarden zijn 1 tot 50.</span><span class="sxs-lookup"><span data-stu-id="68c31-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="68c31-170">De standaardwaarde is 15.</span><span class="sxs-lookup"><span data-stu-id="68c31-170">The default value is 15.</span></span>

   - <span data-ttu-id="68c31-171">`BccEmailAddress`hiermee worden extra BCC-ontvangers opgegeven die een kopie van alle gebruikersinzendingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="68c31-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="68c31-172">De standaardwaarde is leeg (geen extra BCC-ontvangers).</span><span class="sxs-lookup"><span data-stu-id="68c31-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="68c31-173">In dit voorbeeld wordt de 64-bits versie van de invoegtoepassing vanaf het opgegeven pad geïnstalleerd met de standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="68c31-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="68c31-174">In dit voorbeeld wordt de 32-bits versie van de invoegtoepassing vanaf het opgegeven pad geïnstalleerd met de volgende aanvullende instellingen:</span><span class="sxs-lookup"><span data-stu-id="68c31-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="68c31-175">Er kunnen maximaal 20 berichten in één inzending worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="68c31-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="68c31-176">junkreports@contoso.com en hollyd@treyresearch.net ontvangen BCC kopieën van alle inzendingen.</span><span class="sxs-lookup"><span data-stu-id="68c31-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="68c31-177">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="68c31-177">How do you know this worked?</span></span>

<span data-ttu-id="68c31-178">Als u wilt controleren of u de invoegtoepassing Ongewenste e-mailrapportage hebt geïnstalleerd, doet u een van de volgende stappen in Outlook:</span><span class="sxs-lookup"><span data-stu-id="68c31-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="68c31-179">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="68c31-179">Select the message or open the message.</span></span> <span data-ttu-id="68c31-180">Klik op het tabblad **Start** of **Bericht** op het lint op **Ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="68c31-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="68c31-181">**Rapporteren als Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="68c31-181">**Report as Junk**</span></span>
  - <span data-ttu-id="68c31-182">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="68c31-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="68c31-183">**Opties voor meldingen van ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="68c31-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="68c31-184">**Help voor ongewenste e-mail online melden**</span><span class="sxs-lookup"><span data-stu-id="68c31-184">**Report Junk Online Help**</span></span>

  ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="68c31-186">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste en**controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="68c31-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="68c31-187">**Rapporteren als Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="68c31-187">**Report as Junk**</span></span>
  - <span data-ttu-id="68c31-188">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="68c31-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="68c31-189">**Opties voor meldingen van ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="68c31-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="68c31-190">**Help voor ongewenste e-mail online melden**</span><span class="sxs-lookup"><span data-stu-id="68c31-190">**Report Junk Online Help**</span></span>

  ![Ongewenste of phishing-e-mail melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="68c31-192">Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="68c31-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="68c31-193">**Rapporteren als Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="68c31-193">**Report as Junk**</span></span>
  - <span data-ttu-id="68c31-194">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="68c31-194">**Report as Phishing**</span></span>

  ![Meerdere ongewenste of phishing-e-mailberichten melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="68c31-196">Doe de eerdere acties in de map **Ongewenste e-mail** en controleer of de vorige **opties voor ongewenste e-rapportage** nu **geen ongewenste e-mail**zijn.</span><span class="sxs-lookup"><span data-stu-id="68c31-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Geen ongewenste e-mail of phishing melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Geen ongewenste e-mail of phishing melden vanaf de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere niet-ongewenste of phishing-e-mailberichten melden met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="68c31-200">De invoegtoepassing voor het melden van ongewenste e-mail verwijderen</span><span class="sxs-lookup"><span data-stu-id="68c31-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="68c31-201">Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegtoepassing Voor het melden van ongewenste e-mailrapporten te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="68c31-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="68c31-202">**Configuratiescherm**: Druk op de Windows-toets + R. Voer **Run** in het dialoogvenster `control appwiz.cpl` Uitvoeren dat wordt geopend, in en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="68c31-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="68c31-203">Zoek en selecteer **microsoft ongewenste e-mailrapportage-invoegtoepassing** in de lijst en klik op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="68c31-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="68c31-204">**Windows Installer-pakket**: Zoek of download het juiste .msi-bestand en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="68c31-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="68c31-205">**32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="68c31-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="68c31-206">**64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="68c31-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="68c31-207">Selecteer in het dialoogvenster dat wordt weergegeven de optie **Invoegtoepassing voor microsoft-e-mailrapportage voor Outlook verwijderen** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="68c31-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="68c31-208">**Stille modus**: Zoek of download het juiste .msi-bestand.</span><span class="sxs-lookup"><span data-stu-id="68c31-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="68c31-209">Vervang PathToFile\> in \<een opdrachtpromptvenster door de locatie van het MSI-bestand en voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="68c31-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="68c31-210">**32-bits**:</span><span class="sxs-lookup"><span data-stu-id="68c31-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="68c31-211">**64-bits**:</span><span class="sxs-lookup"><span data-stu-id="68c31-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="68c31-212">Wanneer u Outlook opent na het verwijderen, moeten de opties voor ongewenste e-mail, niet voor ongewenste e-mail en phishing-rapportage worden verdwenen.</span><span class="sxs-lookup"><span data-stu-id="68c31-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="68c31-213">Problemen met de invoegtoepassing Ongewenste e-mailrapportage oplossen</span><span class="sxs-lookup"><span data-stu-id="68c31-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="68c31-214">Af en toe u problemen ondervinden met Outlook nadat u de invoegtoepassing Voor ongewenste e-mailrapportage hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="68c31-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="68c31-215">In dit gedeelte worden problemen beschreven die u tegenkomen, samen met tips voor het oplossen van deze problemen.</span><span class="sxs-lookup"><span data-stu-id="68c31-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="68c31-216">Probleemoplossing voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="68c31-216">Troubleshooting for users</span></span>

<span data-ttu-id="68c31-217">U ondervindt een of meer van de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="68c31-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="68c31-218">Er gebeurt niets wanneer u op **Ongewenste e-mail** melden klikt</span><span class="sxs-lookup"><span data-stu-id="68c31-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="68c31-219">Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd</span><span class="sxs-lookup"><span data-stu-id="68c31-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="68c31-220">Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een "onbestelbaar" antwoord</span><span class="sxs-lookup"><span data-stu-id="68c31-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="68c31-221">Ga als volgt te werk om dit probleem op te lossen:</span><span class="sxs-lookup"><span data-stu-id="68c31-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="68c31-222">Outlook sluiten en opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="68c31-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="68c31-223">Maak en verstuur een testbericht en controleer of de ontvanger het bericht heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="68c31-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="68c31-224">Als het probleem blijft bestaan, neemt u contact op met uw beheerder.</span><span class="sxs-lookup"><span data-stu-id="68c31-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="68c31-225">Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)andere methoden die u gebruiken om berichten naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="68c31-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="68c31-226">Probleemoplossing voor beheerders</span><span class="sxs-lookup"><span data-stu-id="68c31-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="68c31-227">Probleem: er verschijnt voortdurend een foutbericht waarin gebruikers wordt gevraagd contact op te nemen met hun systeembeheerder</span><span class="sxs-lookup"><span data-stu-id="68c31-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="68c31-228">Controleer of `LoggingLevel` stel de registersleutel in op de waarde "Verbose":</span><span class="sxs-lookup"><span data-stu-id="68c31-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="68c31-229">**32-bits Outlook op 32-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="68c31-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="68c31-230">**32-bits Outlook op 64-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="68c31-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="68c31-231">**64-bits Outlook:**</span><span class="sxs-lookup"><span data-stu-id="68c31-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="68c31-232">Start Outlook opnieuw op en vraag gebruikers om terug te rapporteren wanneer ze het foutbericht zien.</span><span class="sxs-lookup"><span data-stu-id="68c31-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="68c31-233">Verzamel de loggegevens op de volgende locatie:</span><span class="sxs-lookup"><span data-stu-id="68c31-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="68c31-234">Neem contact op met de technische ondersteuning van Exchange Online Protection en geef hen de loggegevens.</span><span class="sxs-lookup"><span data-stu-id="68c31-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="68c31-235">Probleem: gebruikers hebben ervoor gekozen om geen bevestigingsprompt te ontvangen wanneer ze berichten rapporteren, en nu willen ze de prompt terug</span><span class="sxs-lookup"><span data-stu-id="68c31-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="68c31-236">Maak `ConfirmReportJunk`de registersleutel wih de waarde "True":</span><span class="sxs-lookup"><span data-stu-id="68c31-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="68c31-237">Outlook opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="68c31-237">Restart Outlook.</span></span>
