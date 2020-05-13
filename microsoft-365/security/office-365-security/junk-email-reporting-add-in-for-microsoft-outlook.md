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
ms.openlocfilehash: 5c0b802bea89a0f0f62952261bf0d2864842024f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208825"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="ba89d-103">De invoegtoepassing Voor het melden van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken</span><span class="sxs-lookup"><span data-stu-id="ba89d-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="ba89d-104">Als u momenteel de invoegtoepassing Ongewenste e-mailrapportage niet gebruikt, raden we in plaats daarvan de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md) aan.</span><span class="sxs-lookup"><span data-stu-id="ba89d-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="ba89d-105">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ba89d-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="ba89d-106">Met de invoegtoepassing Ongewenste e-mailrapportage voor Microsoft Outlook kunnen gebruikers valse positieven (goede e-mail gemarkeerd als spam), valse negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba89d-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="ba89d-107">Als uw organisatie geen Exchange Online Protection gebruikt (bijvoorbeeld on-premises Exchange- of e-mailservices dan Exchange Online), heeft het indienen van uw ongewenste e-mailrapport geen invloed op uw spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="ba89d-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="ba89d-108">In dit onderwerp wordt uitgelegd hoe u de invoegtoepassing Ongewenste e-mailrapportage installeert en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ba89d-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ba89d-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ba89d-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ba89d-110">Zie de invoegtoepassing Voor het rapporteren van [ongewenste e-mail](#install-the-junk-email-reporting-add-in) later in dit onderwerp als u de invoegtoepassing Voor ongewenste e-mailrapportage wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="ba89d-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="ba89d-111">De invoegtoepassing Voor ongewenste e-mailrapportage werkt met de volgende versies van Outlook:</span><span class="sxs-lookup"><span data-stu-id="ba89d-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="ba89d-112">Outlook 2013 of hoger</span><span class="sxs-lookup"><span data-stu-id="ba89d-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="ba89d-113">Outlook opgenomen in Microsoft 365 Apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="ba89d-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="ba89d-114">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ba89d-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="ba89d-115">De invoegtoepassing Ongewenste e-mailrapportage gebruiken om spam- en phishingberichten te melden</span><span class="sxs-lookup"><span data-stu-id="ba89d-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="ba89d-116">Voor berichten in het Postvak IN of een andere e-mailmap, met uitzondering van Ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="ba89d-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="ba89d-117">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="ba89d-117">Select the message or open the message.</span></span> <span data-ttu-id="ba89d-118">Klik op het tabblad **Start** of **Bericht** op het lint op **Ongewenste e-mail**en selecteer **Vervolgens Rapporteren als ongewenste e-mail** of **Rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="ba89d-120">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail**en selecteer **Vervolgens Rapporteren als ongewenste e-mail** of Rapport als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste of phishing-e-mail melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="ba89d-122">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als ongewenste e-mail** of **Rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Meerdere ongewenste of phishing-e-mailberichten melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="ba89d-124">Lees in het dialoogvenster dat wordt weergegeven de informatie en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ba89d-125">Als u van gedachten verandert, klikt u op **Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="ba89d-125">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport als pictogram ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="ba89d-128">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ba89d-128">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder.</span></span> <span data-ttu-id="ba89d-129">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ba89d-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="ba89d-130">De invoegtoepassing Ongewenste e-mailrapportage gebruiken om niet-spam- en phishingberichten te melden vanuit de map Ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="ba89d-130">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="ba89d-131">Gebruik in de map Ongewenste e-mail een van de volgende methoden om valse positieven of phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="ba89d-131">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="ba89d-132">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="ba89d-132">Select the message or open the message.</span></span> <span data-ttu-id="ba89d-133">Klik op het tabblad **Start** of **Bericht** op het lint op **Geen ongewenstee informatie**en selecteer Vervolgens Rapporteren als Niet ongewenste **e-mail** of **Rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-133">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Geen ongewenste e-mail of phishing melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="ba89d-135">Klik met de rechtermuisknop op het bericht, klik op **Ongewenste e-mail**en selecteer **Rapporteren als Niet ongewenste e-mail** of Rapport als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-135">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Geen ongewenste e-mail of phishing melden vanaf de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="ba89d-137">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als Niet ongewenste e-mail** of Meld als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-137">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Meerdere niet-ongewenste of phishing-e-mailberichten melden met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="ba89d-139">Lees in het dialoogvenster dat wordt weergegeven de informatie en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-139">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ba89d-140">Als u van gedachten verandert, klikt u op **Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="ba89d-140">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport als niet-ongewenste dialoogvenster](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="ba89d-143">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ba89d-143">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder.</span></span> <span data-ttu-id="ba89d-144">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ba89d-144">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="ba89d-145">De invoegtoepassing Voor het melden van ongewenste e-mail installeren</span><span class="sxs-lookup"><span data-stu-id="ba89d-145">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="ba89d-146">U moet beheerdersbevoegdheden hebben op de computer waar u de invoegtoepassing installeert.</span><span class="sxs-lookup"><span data-stu-id="ba89d-146">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="ba89d-147">Ga naar <https://www.microsoft.com/download/details.aspx?id=18275> en download het juiste .msi-bestand voor uw versie van Office naar een locatie die gemakkelijk te vinden is:</span><span class="sxs-lookup"><span data-stu-id="ba89d-147">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="ba89d-148">**32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ba89d-148">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="ba89d-149">**64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ba89d-149">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="ba89d-150">Voor Outlook 2013 of hoger is de enige voorwaarde het Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="ba89d-150">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="ba89d-151">In Windows 10 installeert u het .NET Framework 2.0 niet vanaf een download.</span><span class="sxs-lookup"><span data-stu-id="ba89d-151">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="ba89d-152">De invoegtoepassing voor ongewenste e-mailrapportage installeren met de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="ba89d-152">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="ba89d-153">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="ba89d-153">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="ba89d-154">Controleer in Windows 10 of het .NET Framework 2.0 is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ba89d-154">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="ba89d-155">Zie Het [.NET Framework 3.5 inschakelen in het Configuratiescherm](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)voor instructies .</span><span class="sxs-lookup"><span data-stu-id="ba89d-155">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="ba89d-156">Zoek het .msi-bestand dat je hebt gedownload en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="ba89d-156">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="ba89d-157">Klik op de pagina **Invoegtoepassing Installatie van ongewenste e-mail van Microsoft** op de pagina Welkom bij Microsoft Ongewenste E-mailrapportage op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-157">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="ba89d-158">Bekijk de licentieovereenkomst, klik op **Ik accepteer de voorwaarden in de licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-158">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="ba89d-159">Wanneer de wizard is voltooid, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-159">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="ba89d-160">Outlook starten.</span><span class="sxs-lookup"><span data-stu-id="ba89d-160">Start Outlook.</span></span>

<span data-ttu-id="ba89d-161">Zoek naar de knop **Ongewenstee inhoud** op het outlook-lint.</span><span class="sxs-lookup"><span data-stu-id="ba89d-161">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="ba89d-162">U nu ongewenste e-mailberichten aan Microsoft rapporteren door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste e-mail** melden te klikken.</span><span class="sxs-lookup"><span data-stu-id="ba89d-162">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="ba89d-163">Kies de pijl-omlaag naast **Ongewenstee opties** voor meer opties, zoals **Melden als Phishing** als u phishing-scam-e-mails aan Microsoft wilt melden.</span><span class="sxs-lookup"><span data-stu-id="ba89d-163">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="ba89d-164">In uw map met ongewenste e-mail u ook verwijderen, **Geen ongewenste e-mail** melden als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ba89d-164">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="ba89d-165">De invoegtoepassing voor ongewenste e-mailrapportage installeren met de stille modus</span><span class="sxs-lookup"><span data-stu-id="ba89d-165">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="ba89d-166">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="ba89d-166">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="ba89d-167">Installeer in Windows 10 het .NET Framework 2.0 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="ba89d-167">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="ba89d-168">Als u de invoegtoepassing zonder gebruikersinteractie wilt installeren, opent u een opdrachtprompt en gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ba89d-168">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="ba89d-169">`MaxMessageSelection`hiermee geeft u het maximumaantal berichten op dat u voor één inzending selecteren.</span><span class="sxs-lookup"><span data-stu-id="ba89d-169">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="ba89d-170">Geldige waarden zijn 1 tot 50.</span><span class="sxs-lookup"><span data-stu-id="ba89d-170">Valid values are from 1 to 50.</span></span> <span data-ttu-id="ba89d-171">De standaardwaarde is 15.</span><span class="sxs-lookup"><span data-stu-id="ba89d-171">The default value is 15.</span></span>

   - <span data-ttu-id="ba89d-172">`BccEmailAddress`hiermee worden extra BCC-ontvangers opgegeven die een kopie van alle gebruikersinzendingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ba89d-172">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="ba89d-173">De standaardwaarde is leeg (geen extra BCC-ontvangers).</span><span class="sxs-lookup"><span data-stu-id="ba89d-173">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="ba89d-174">In dit voorbeeld wordt de 64-bits versie van de invoegtoepassing vanaf het opgegeven pad geïnstalleerd met de standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="ba89d-174">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="ba89d-175">In dit voorbeeld wordt de 32-bits versie van de invoegtoepassing vanaf het opgegeven pad geïnstalleerd met de volgende aanvullende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ba89d-175">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="ba89d-176">Er kunnen maximaal 20 berichten in één inzending worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ba89d-176">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="ba89d-177">junkreports@contoso.com en hollyd@treyresearch.net ontvangen BCC kopieën van alle inzendingen.</span><span class="sxs-lookup"><span data-stu-id="ba89d-177">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ba89d-178">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="ba89d-178">How do you know this worked?</span></span>

<span data-ttu-id="ba89d-179">Als u wilt controleren of u de invoegtoepassing Ongewenste e-mailrapportage hebt geïnstalleerd, doet u een van de volgende stappen in Outlook:</span><span class="sxs-lookup"><span data-stu-id="ba89d-179">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="ba89d-180">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="ba89d-180">Select the message or open the message.</span></span> <span data-ttu-id="ba89d-181">Klik op het tabblad **Start** of **Bericht** op het lint op **Ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="ba89d-181">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ba89d-182">**Rapporteren als Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ba89d-182">**Report as Junk**</span></span>
  - <span data-ttu-id="ba89d-183">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="ba89d-183">**Report as Phishing**</span></span>
  - <span data-ttu-id="ba89d-184">**Opties voor meldingen van ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ba89d-184">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="ba89d-185">**Help voor ongewenste e-mail online melden**</span><span class="sxs-lookup"><span data-stu-id="ba89d-185">**Report Junk Online Help**</span></span>

  ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="ba89d-187">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste en**controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="ba89d-187">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ba89d-188">**Rapporteren als Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ba89d-188">**Report as Junk**</span></span>
  - <span data-ttu-id="ba89d-189">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="ba89d-189">**Report as Phishing**</span></span>
  - <span data-ttu-id="ba89d-190">**Opties voor meldingen van ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ba89d-190">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="ba89d-191">**Help voor ongewenste e-mail online melden**</span><span class="sxs-lookup"><span data-stu-id="ba89d-191">**Report Junk Online Help**</span></span>

  ![Ongewenste of phishing-e-mail melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="ba89d-193">Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="ba89d-193">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ba89d-194">**Rapporteren als Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ba89d-194">**Report as Junk**</span></span>
  - <span data-ttu-id="ba89d-195">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="ba89d-195">**Report as Phishing**</span></span>

  ![Meerdere ongewenste of phishing-e-mailberichten melden vanaf de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="ba89d-197">Doe de eerdere acties in de map **Ongewenste e-mail** en controleer of de vorige **opties voor ongewenste e-rapportage** nu **geen ongewenste e-mail**zijn.</span><span class="sxs-lookup"><span data-stu-id="ba89d-197">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Geen ongewenste e-mail of phishing melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Geen ongewenste e-mail of phishing melden vanaf de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere niet-ongewenste of phishing-e-mailberichten melden met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="ba89d-201">De invoegtoepassing voor het melden van ongewenste e-mail verwijderen</span><span class="sxs-lookup"><span data-stu-id="ba89d-201">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="ba89d-202">Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegtoepassing Voor het melden van ongewenste e-mailrapporten te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="ba89d-202">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="ba89d-203">**Configuratiescherm**: Druk op de Windows-toets + R. Voer in het dialoogvenster **Uitvoeren** dat wordt geopend, in `control appwiz.cpl` en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-203">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="ba89d-204">Zoek en selecteer **microsoft ongewenste e-mailrapportage-invoegtoepassing** in de lijst en klik op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-204">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="ba89d-205">**Windows Installer-pakket**: Zoek of download het juiste .msi-bestand en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="ba89d-205">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="ba89d-206">**32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ba89d-206">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="ba89d-207">**64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ba89d-207">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="ba89d-208">Selecteer in het dialoogvenster dat wordt weergegeven de optie **Invoegtoepassing voor microsoft-e-mailrapportage voor Outlook verwijderen** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ba89d-208">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="ba89d-209">**Stille modus**: Zoek of download het juiste .msi-bestand.</span><span class="sxs-lookup"><span data-stu-id="ba89d-209">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="ba89d-210">Vervang PathToFile in een opdrachtpromptvenster \< door de locatie van het \> MSI-bestand en voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="ba89d-210">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="ba89d-211">**32-bits**:</span><span class="sxs-lookup"><span data-stu-id="ba89d-211">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="ba89d-212">**64-bits**:</span><span class="sxs-lookup"><span data-stu-id="ba89d-212">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="ba89d-213">Wanneer u Outlook opent na het verwijderen, moeten de opties voor ongewenste e-mail, niet voor ongewenste e-mail en phishing-rapportage worden verdwenen.</span><span class="sxs-lookup"><span data-stu-id="ba89d-213">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="ba89d-214">Problemen met de invoegtoepassing Ongewenste e-mailrapportage oplossen</span><span class="sxs-lookup"><span data-stu-id="ba89d-214">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="ba89d-215">Af en toe u problemen ondervinden met Outlook nadat u de invoegtoepassing Voor ongewenste e-mailrapportage hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ba89d-215">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="ba89d-216">In dit gedeelte worden problemen beschreven die u tegenkomen, samen met tips voor het oplossen van deze problemen.</span><span class="sxs-lookup"><span data-stu-id="ba89d-216">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="ba89d-217">Probleemoplossing voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="ba89d-217">Troubleshooting for users</span></span>

<span data-ttu-id="ba89d-218">U ondervindt een of meer van de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="ba89d-218">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="ba89d-219">Er gebeurt niets wanneer u op **Ongewenste e-mail** melden klikt</span><span class="sxs-lookup"><span data-stu-id="ba89d-219">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="ba89d-220">Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd</span><span class="sxs-lookup"><span data-stu-id="ba89d-220">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="ba89d-221">Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een "onbestelbaar" antwoord</span><span class="sxs-lookup"><span data-stu-id="ba89d-221">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="ba89d-222">Ga als volgt te werk om dit probleem op te lossen:</span><span class="sxs-lookup"><span data-stu-id="ba89d-222">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="ba89d-223">Outlook sluiten en opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="ba89d-223">Close and restart Outlook.</span></span>
2. <span data-ttu-id="ba89d-224">Maak en verstuur een testbericht en controleer of de ontvanger het bericht heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ba89d-224">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="ba89d-225">Als het probleem blijft bestaan, neemt u contact op met uw beheerder.</span><span class="sxs-lookup"><span data-stu-id="ba89d-225">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="ba89d-226">Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)andere methoden die u gebruiken om berichten naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="ba89d-226">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="ba89d-227">Probleemoplossing voor beheerders</span><span class="sxs-lookup"><span data-stu-id="ba89d-227">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="ba89d-228">Probleem: er verschijnt voortdurend een foutbericht waarin gebruikers wordt gevraagd contact op te nemen met hun systeembeheerder</span><span class="sxs-lookup"><span data-stu-id="ba89d-228">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="ba89d-229">Controleer of stel de registersleutel in `LoggingLevel` op de waarde "Verbose":</span><span class="sxs-lookup"><span data-stu-id="ba89d-229">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="ba89d-230">**32-bits Outlook op 32-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="ba89d-230">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="ba89d-231">**32-bits Outlook op 64-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="ba89d-231">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="ba89d-232">**64-bits Outlook:**</span><span class="sxs-lookup"><span data-stu-id="ba89d-232">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="ba89d-233">Start Outlook opnieuw op en vraag gebruikers om terug te rapporteren wanneer ze het foutbericht zien.</span><span class="sxs-lookup"><span data-stu-id="ba89d-233">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="ba89d-234">Verzamel de loggegevens op de volgende locatie:</span><span class="sxs-lookup"><span data-stu-id="ba89d-234">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="ba89d-235">Neem contact op met de technische ondersteuning van Exchange Online Protection en geef hen de loggegevens.</span><span class="sxs-lookup"><span data-stu-id="ba89d-235">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="ba89d-236">Probleem: gebruikers hebben ervoor gekozen om geen bevestigingsprompt te ontvangen wanneer ze berichten rapporteren, en nu willen ze de prompt terug</span><span class="sxs-lookup"><span data-stu-id="ba89d-236">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="ba89d-237">Maak de `ConfirmReportJunk` registersleutel wih de waarde "True":</span><span class="sxs-lookup"><span data-stu-id="ba89d-237">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="ba89d-238">Outlook opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="ba89d-238">Restart Outlook.</span></span>
