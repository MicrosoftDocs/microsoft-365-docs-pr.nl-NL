---
title: De invoegtoepassing Ongewenste e-mailrapportage voor Microsoft Outlook installeren en gebruiken
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
description: Meer informatie over het installeren en gebruiken van de Microsoft Junk Email Reporting-rapportage om spam-, niet-spam- en phishingberichten aan Microsoft te rapporteren.
ms.openlocfilehash: 54b0fb634333ccb180870ab1fcc6160fd133f81e
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560519"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="9d6ab-103">De invoegtoepassing Ongewenste e-mailrapportage voor Microsoft Outlook installeren en gebruiken</span><span class="sxs-lookup"><span data-stu-id="9d6ab-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="9d6ab-104">Als u momenteel de invoegtoepassing Ongewenste e-mailrapportage niet gebruikt, raden we u in plaats daarvan de [invoegtoepassing Rapportbericht aan.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="9d6ab-105">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9d6ab-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="9d6ab-106">Met de add-invoeging voor ongewenste e-mailrapportage voor Microsoft Outlook kunnen gebruikers valse positieven (goede e-mail gemarkeerd als spam), valse negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="9d6ab-107">Als uw organisatie geen Exchange Online Protection gebruikt (bijvoorbeeld on-premises Exchange of andere e-mailservices dan Exchange Online), heeft uw indiening van ongewenste e-mailverslagen geen invloed op uw spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="9d6ab-108">In dit onderwerp wordt uitgelegd hoe u de invoegtoepassing Ongewenste e-mailrapportage installeert en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9d6ab-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="9d6ab-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9d6ab-110">Zie de [invoegtoepassing Ongewenste e-mailrapportage](#install-the-junk-email-reporting-add-in) installeren in dit onderwerp om de invoegtoepassing Ongewenste e-mailrapportage te installeren.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="9d6ab-111">De invoegtoepassing Rapportage voor ongewenste e-mail werkt met de volgende versies van Outlook:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="9d6ab-112">Outlook 2013 of hoger</span><span class="sxs-lookup"><span data-stu-id="9d6ab-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="9d6ab-113">Outlook inbegrepen bij Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d6ab-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="9d6ab-114">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="9d6ab-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="9d6ab-115">De invoegtoepassing Ongewenste e-mailrapportage gebruiken om spam- en phishingberichten te melden</span><span class="sxs-lookup"><span data-stu-id="9d6ab-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="9d6ab-116">Voor berichten in het Postvak IN of een andere e-mailmap, behalve ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="9d6ab-117">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-117">Select the message or open the message.</span></span> <span data-ttu-id="9d6ab-118">Klik op het tabblad **Start** of **bericht** op het lint op **Ongewenste e-mail**en selecteer **Rapporteren als ongewenste e-mail** of **rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![E-mail met ongewenste e-mail of phishing melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="9d6ab-120">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail**en selecteer **Rapporteren als ongewenste e-mail** of rapport als **phishing**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![E-mail met de rechtermuisknop melden](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="9d6ab-122">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als ongewenste e-mail** of **rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Meerdere ongewenste e-mailberichten melden met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="9d6ab-124">Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="9d6ab-125">Als u van gedachten verandert, klikt u op **Niet rapporteren**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-125">If you change your mind, click **Don't Report**.</span></span>

   ![Dialoogvenster Rapporteren als ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialoogvenster rapporteren als phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="9d6ab-128">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="9d6ab-129">Verplaatst naar de map Ongewenste e-mail als deze als spam is gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="9d6ab-130">Verwijderd als het werd gemeld als phishing.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="9d6ab-131">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de verzonden berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="9d6ab-132">De invoegtoepassing Ongewenste e-mailrapportage gebruiken om niet-spam- en phishingberichten te rapporteren vanuit de map Ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="9d6ab-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="9d6ab-133">Gebruik in de map Ongewenste e-mail een van de volgende methoden om spamalmerk-positieven of phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="9d6ab-134">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-134">Select the message or open the message.</span></span> <span data-ttu-id="9d6ab-135">Klik op het tabblad **Start** of **bericht** op het lint op **Niet ongewenste e-mail**en selecteer Rapporteren als **niet-ongewenste e-mail** of **rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Geen ongewenste e-mail of phishing-e-mail melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="9d6ab-137">Klik met de rechtermuisknop op het bericht, klik op **Ongewenste e-mail**en selecteer **Rapporteren als niet-ongewenste e-mail** of **rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Niet ongewenste e-mail of phishing-e-mail melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="9d6ab-139">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als niet-ongewenste e-mail** of **rapport als phishing**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Meerdere niet-ongewenste e-mailberichten of phishing-e-mailberichten melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="9d6ab-141">Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="9d6ab-142">Als u van gedachten verandert, klikt u op **Niet rapporteren**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-142">If you change your mind, click **Don't Report**.</span></span>

   ![Dialoogvenster Rapporteren als niet-ongewenste e-mail](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialoogvenster rapporteren als phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="9d6ab-145">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="9d6ab-146">Verplaatst naar de map Ongewenste e-mail als deze als spam is gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="9d6ab-147">Verwijderd als het werd gemeld als phishing.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="9d6ab-148">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de verzonden berichten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="9d6ab-149">De invoegtoepassing Ongewenste e-mailrapportage installeren</span><span class="sxs-lookup"><span data-stu-id="9d6ab-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="9d6ab-150">U moet beheerdersbevoegdheden hebben op de computer waar u de invoegtoepassing installeert.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="9d6ab-151">Ga naar <https://www.microsoft.com/download/details.aspx?id=18275> en download het juiste .msi-bestand voor uw versie van Office naar een locatie die gemakkelijk te vinden is:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="9d6ab-152">**32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d6ab-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="9d6ab-153">**64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d6ab-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="9d6ab-154">Voor Outlook 2013 of hoger is de enige vereiste de Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="9d6ab-155">In Windows 10 installeert u de .NET Framework 2.0 niet vanaf een download.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="9d6ab-156">De invoegtoepassing Rapportage voor ongewenste e-mail installeren met de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="9d6ab-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="9d6ab-157">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="9d6ab-158">Controleer in Windows 10 of de .NET Framework 2.0 is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="9d6ab-159">Zie Het [.NET Framework 3.5 inschakelen in het Configuratiescherm](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="9d6ab-160">Zoek het .msi-bestand dat je hebt gedownload en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="9d6ab-161">Klik op de pagina **Invoegtoepassingsrapportage voor ongewenste e-mailrapportage** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="9d6ab-162">Controleer de licentieovereenkomst, klik op **Ik accepteer de voorwaarden in de licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="9d6ab-163">Wanneer de wizard is voltooid, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="9d6ab-164">Start Outlook.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-164">Start Outlook.</span></span>

<span data-ttu-id="9d6ab-165">Zoek naar de knop **Ongewenste e-mail** op het Outlook-lint.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-165">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="9d6ab-166">U nu ongewenste e-mailberichten aan Microsoft rapporteren door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste e-mailrapport** te klikken.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-166">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="9d6ab-167">Kies de pijl-omlaag naast **Ongewenste e-mail** voor meer opties, zoals **Rapporteren als phishing** als u phishing-scam-e-mails wilt melden aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-167">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="9d6ab-168">In uw map met ongewenste e-mail u ook **ongewenste e-mail** melden als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-168">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="9d6ab-169">De invoegtoepassing Ongewenste e-mailrapportage installeren met de stille modus</span><span class="sxs-lookup"><span data-stu-id="9d6ab-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="9d6ab-170">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="9d6ab-171">Installeer in Windows 10 de .NET Framework 2.0 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="9d6ab-172">Als u de invoegtoepassing wilt installeren zonder interactie van de gebruiker, opent u een opdrachtprompt en gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="9d6ab-173">`MaxMessageSelection`hiermee geeft u het maximum aantal berichten op dat u selecteren voor één inzending.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="9d6ab-174">Geldige waarden zijn van 1 tot 50.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="9d6ab-175">De standaardwaarde is 15.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-175">The default value is 15.</span></span>

   - <span data-ttu-id="9d6ab-176">`BccEmailAddress`geeft extra BCC-ontvangers op die een kopie van alle gebruikersinzendingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="9d6ab-177">De standaardwaarde is leeg (geen extra BCC-ontvangers).</span><span class="sxs-lookup"><span data-stu-id="9d6ab-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="9d6ab-178">In dit voorbeeld wordt de 64-bits versie van de invoegtoepassing vanaf het opgegeven pad met de standaardinstellingen geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="9d6ab-179">In dit voorbeeld wordt de 32-bits versie van de invoegtoepassing vanaf het opgegeven pad met de volgende extra instellingen geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="9d6ab-180">Maximaal 20 berichten kunnen in één inzending worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="9d6ab-181">junkreports@contoso.com en hollyd@treyresearch.net ontvangen BCC kopieën van alle inzendingen.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9d6ab-182">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="9d6ab-182">How do you know this worked?</span></span>

<span data-ttu-id="9d6ab-183">Als u wilt controleren of u de invoegtoepassing Voor rapportage voor ongewenste e-mail hebt geïnstalleerd, voert u een van de volgende stappen uit in Outlook:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="9d6ab-184">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-184">Select the message or open the message.</span></span> <span data-ttu-id="9d6ab-185">Klik op het tabblad **Start** of **bericht** op het lint op **Ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="9d6ab-186">**Rapporteren als ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-186">**Report as Junk**</span></span>
  - <span data-ttu-id="9d6ab-187">**Rapporteren als phishing**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="9d6ab-188">**Opties voor ongewenste rapportage**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="9d6ab-189">**Help voor ongewenste e-mail melden**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-189">**Report Junk Online Help**</span></span>

  ![E-mail met ongewenste e-mail of phishing melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="9d6ab-191">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="9d6ab-192">**Rapporteren als ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-192">**Report as Junk**</span></span>
  - <span data-ttu-id="9d6ab-193">**Rapporteren als phishing**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="9d6ab-194">**Opties voor ongewenste rapportage**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="9d6ab-195">**Help voor ongewenste e-mail melden**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-195">**Report Junk Online Help**</span></span>

  ![E-mail met de rechtermuisknop melden](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="9d6ab-197">Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="9d6ab-198">**Rapporteren als ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-198">**Report as Junk**</span></span>
  - <span data-ttu-id="9d6ab-199">**Rapporteren als phishing**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-199">**Report as Phishing**</span></span>

  ![Meerdere ongewenste e-mailberichten melden met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="9d6ab-201">Doe de vorige acties in de map **Ongewenste e-mail** en controleer of de vorige opties **voor ongewenste e-mail** nu **geen ongewenste e-mail**zijn.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Geen ongewenste e-mail of phishing-e-mail melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Niet ongewenste e-mail of phishing-e-mail melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere niet-ongewenste e-mailberichten of phishing-e-mailberichten melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="9d6ab-205">De invoegtoepassing Rapportage voor ongewenste e-mail verwijderen</span><span class="sxs-lookup"><span data-stu-id="9d6ab-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="9d6ab-206">Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegtoepassing Voor de rapportage voor ongewenste e-mail te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="9d6ab-207">**Configuratiescherm**: Druk op de Windows-toets + R. Voer in het dialoogvenster **Uitvoeren** dat wordt geopend, in `control appwiz.cpl` en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="9d6ab-208">Zoek en selecteer **Microsoft Junk Email Reporting Add-in** in de lijst en klik vervolgens op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="9d6ab-209">**Windows Installer-pakket**: zoek of download het juiste .msi-bestand en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="9d6ab-210">**32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d6ab-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="9d6ab-211">**64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="9d6ab-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="9d6ab-212">Selecteer in het dialoogvenster dat wordt weergegeven de optie **Microsoft-rapportage voor ongewenste e-mail voor Outlook verwijderen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="9d6ab-213">**Silent Mode**: Zoek of download het juiste .msi-bestand.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="9d6ab-214">Vervang in een opdrachtpromptvenster \<PathToFile\> de locatie van het .msi-bestand en voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="9d6ab-215">**32-bits**:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="9d6ab-216">**64-bits**:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="9d6ab-217">Wanneer u Outlook opent na het verwijderen, moeten de opties voor ongewenste e-mail, niet ongewenste e-mail en phishing-rapportage zijn verdwenen.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="9d6ab-218">Problemen met de invoegtoepassing Ongewenste e-mailrapportage oplossen</span><span class="sxs-lookup"><span data-stu-id="9d6ab-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="9d6ab-219">Soms u problemen ondervinden met Outlook nadat u de invoegtoepassing Voor de rapportage voor ongewenste e-mail hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="9d6ab-220">In deze sectie worden problemen beschreven die u mogelijk tegenkomt, samen met tips voor het oplossen van deze problemen.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="9d6ab-221">Probleemoplossing voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="9d6ab-221">Troubleshooting for users</span></span>

<span data-ttu-id="9d6ab-222">U ondervindt een of meer van de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="9d6ab-223">Er gebeurt niets wanneer u op **Ongewenste e-mail rapporteren klikt**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="9d6ab-224">Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd</span><span class="sxs-lookup"><span data-stu-id="9d6ab-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="9d6ab-225">Gemelde ongewenste e-mail kan niet worden bezorgd vanwege een "onbestelbaar" antwoord</span><span class="sxs-lookup"><span data-stu-id="9d6ab-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="9d6ab-226">Ga als volgt te werk om dit probleem op te lossen:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="9d6ab-227">Outlook sluiten en opnieuw starten.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="9d6ab-228">Maak en verzend een testbericht en controleer of de ontvanger het bericht heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="9d6ab-229">Als het probleem blijft bestaan, neemt u contact op met uw beheerder.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="9d6ab-230">Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)andere methoden die u gebruiken om berichten naar Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="9d6ab-231">Probleemoplossing voor beheerders</span><span class="sxs-lookup"><span data-stu-id="9d6ab-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="9d6ab-232">Probleem: er verschijnt voortdurend een foutbericht waarin gebruikers wordt gevraagd contact op te nemen met hun systeembeheerder</span><span class="sxs-lookup"><span data-stu-id="9d6ab-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="9d6ab-233">Controleer of stel de registersleutel in `LoggingLevel` op de waarde "Verbose":</span><span class="sxs-lookup"><span data-stu-id="9d6ab-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="9d6ab-234">**32-bits Outlook op 32-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="9d6ab-235">**32-bits Outlook op 64-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="9d6ab-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="9d6ab-236">**64-bits Outlook**:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="9d6ab-237">Start Outlook opnieuw op en vraag gebruikers om verslag uit te brengen wanneer ze het foutbericht zien.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="9d6ab-238">Verzamel de loggegevens die op de volgende locatie zijn gevonden:</span><span class="sxs-lookup"><span data-stu-id="9d6ab-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="9d6ab-239">Neem contact op met de technische ondersteuning van Exchange Online Protection en geef ze de loggegevens.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="9d6ab-240">Probleem: gebruikers die zijn geselecteerd om geen bevestigingsprompt te ontvangen wanneer ze berichten rapporteren en willen nu de prompt terug</span><span class="sxs-lookup"><span data-stu-id="9d6ab-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="9d6ab-241">Maak de `ConfirmReportJunk` registersleutel met de waarde 'Waar':</span><span class="sxs-lookup"><span data-stu-id="9d6ab-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="9d6ab-242">Start Outlook opnieuw.</span><span class="sxs-lookup"><span data-stu-id="9d6ab-242">Restart Outlook.</span></span>
