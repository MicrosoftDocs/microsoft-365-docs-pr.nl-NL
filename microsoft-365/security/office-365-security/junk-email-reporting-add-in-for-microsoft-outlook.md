---
title: De invoegtoepassing voor het rapporteren van ongewenste E-mail voor Microsoft Outlook installeren en gebruiken
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Informatie over het installeren en gebruiken van de invoegtoepassing voor het rapporteren van ongewenste E-mail om spam, geen spam en phishing-berichten te rapporteren aan Microsoft.
ms.openlocfilehash: 096bd83c53149360e6cdd3ba8e73aacce5b1106f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199683"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="e8412-103">De invoegtoepassing voor het rapporteren van ongewenste E-mail voor Microsoft Outlook installeren en gebruiken</span><span class="sxs-lookup"><span data-stu-id="e8412-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="e8412-104">Als u momenteel de invoegtoepassing voor het rapporteren van ongewenste E-mail niet gebruikt, wordt u aangeraden de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e8412-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="e8412-105">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e8412-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="e8412-106">Met de invoegtoepassing voor het rapporteren van ongewenste E-mail voor Microsoft Outlook kunnen gebruikersfout berichten verzenden (goede e-mailberichten die als spam zijn gemarkeerd), onjuiste negatieven (onjuiste e-mail toegestaan) en phishingberichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e8412-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="e8412-107">Als uw organisatie Exchange Online Protection niet gebruikt (bijvoorbeeld on-premises Exchange of e-mailservices die niet werken met Exchange Online), heeft uw verzenden van het rapport ongewenste e-mail geen gevolgen voor spamfilters.</span><span class="sxs-lookup"><span data-stu-id="e8412-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="e8412-108">In dit onderwerp wordt uitgelegd hoe u de invoegtoepassing voor het rapporteren van ongewenste E-mail installeert en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e8412-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8412-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e8412-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8412-110">Als u de invoegtoepassing voor het rapporteren van ongewenste E-mail wilt installeren, raadpleegt u de sectie [invoegtoepassing voor ongewenste E-mail installeren](#install-the-junk-email-reporting-add-in) verderop in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="e8412-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="e8412-111">De invoegtoepassing voor het rapporteren van ongewenste E-mail werkt met de volgende versies van Outlook:</span><span class="sxs-lookup"><span data-stu-id="e8412-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="e8412-112">Outlook 2013 of later</span><span class="sxs-lookup"><span data-stu-id="e8412-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="e8412-113">Outlook inbegrepen in Microsoft 365 apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e8412-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="e8412-114">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over het rapporteren van berichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e8412-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="e8412-115">De invoegtoepassing voor het rapporteren van ongewenste E-mail gebruiken om spam en phishing-berichten te rapporteren</span><span class="sxs-lookup"><span data-stu-id="e8412-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="e8412-116">Voor berichten in het postvak in of een andere e-mailmap met uitzondering van ongewenste E-mail, gebruikt u een van de volgende methoden om spam en phishing-berichten te rapporteren:</span><span class="sxs-lookup"><span data-stu-id="e8412-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="e8412-117">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="e8412-117">Select the message or open the message.</span></span> <span data-ttu-id="e8412-118">Klik op het lint op het tabblad **Start** of **bericht** op **ongewenste e-mail**en selecteer vervolgens **rapporteren als ongewenste e-mail** of **rapporteren als phishing**.</span><span class="sxs-lookup"><span data-stu-id="e8412-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste e-mail of malafide e-mail melden via het lint](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="e8412-120">Klik met de rechtermuisknop op het bericht, selecteer **ongewenste e-mail**en selecteer vervolgens **rapporteren als ongewenste e-mail** of **rapporteren als phishing**.</span><span class="sxs-lookup"><span data-stu-id="e8412-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste e-mail of malafide e-mail melden met de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="e8412-122">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer vervolgens **rapporteren als ongewenste e-mail** of **rapporteren als phishing**.</span><span class="sxs-lookup"><span data-stu-id="e8412-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Meerdere spam-en malafide e-mailberichten rapporteren met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="e8412-124">In het dialoogvenster dat wordt weergegeven, leest u de informatie en klikt u op **rapport**.</span><span class="sxs-lookup"><span data-stu-id="e8412-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="e8412-125">Als u van gedachten verandert, klikt u op **niet melden**.</span><span class="sxs-lookup"><span data-stu-id="e8412-125">If you change your mind, click **Don't Report**.</span></span>

   ![Melden als ongewenst dialoogvenster](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Melden als phishing-dialoogvenster](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="e8412-128">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="e8412-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="e8412-129">Verplaatst naar de map Ongewenste E-mail als deze als spam is gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e8412-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="e8412-130">Verwijderd als phishing werd gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e8412-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="e8412-131">Als u wilt controleren of de berichten zijn verzonden, opent u de map **verzonden items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e8412-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="e8412-132">De invoegtoepassing voor het rapporteren van ongewenste E-mail gebruiken om niet-spamberichten en phishingberichten te rapporteren vanuit de map Ongewenste E-mail</span><span class="sxs-lookup"><span data-stu-id="e8412-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="e8412-133">Gebruik een van de volgende methoden in de map Ongewenste E-mail om spam te rapporteren met een fout positief of malafide bericht:</span><span class="sxs-lookup"><span data-stu-id="e8412-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="e8412-134">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="e8412-134">Select the message or open the message.</span></span> <span data-ttu-id="e8412-135">Klik op het lint op het tabblad **Start** of **bericht** op **geen ongewenste E-mail**en selecteer vervolgens **als niet-ongewenste e-mail melden** of **rapporteren als phishing**.</span><span class="sxs-lookup"><span data-stu-id="e8412-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Ongewenst of malafide e-mail melden via het lint in de map Ongewenste E-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="e8412-137">Klik met de rechtermuisknop op het bericht en klik op **ongewenste e-mail**en selecteer vervolgens **rapporteren als geen ongewenste e-mail** of **Meld als phishing**.</span><span class="sxs-lookup"><span data-stu-id="e8412-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Meld geen ongewenste e-mail of malafide e-mail van met de rechtermuisknop in de map Ongewenste E-mail.](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="e8412-139">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer vervolgens **rapporteren als geen ongewenste e-mail** of **rapporteren als phishing**.</span><span class="sxs-lookup"><span data-stu-id="e8412-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Meld u niet af met de rechtermuisknop op de map Ongewenste e-mail of Meld u niet af met ongewenste e-mail.](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="e8412-141">In het dialoogvenster dat wordt weergegeven, leest u de informatie en klikt u op **rapport**.</span><span class="sxs-lookup"><span data-stu-id="e8412-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="e8412-142">Als u van gedachten verandert, klikt u op **niet melden**.</span><span class="sxs-lookup"><span data-stu-id="e8412-142">If you change your mind, click **Don't Report**.</span></span>

   ![Dialoogvenster als niet-ongewenste e-mail rapporteren](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Melden als phishing-dialoogvenster](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="e8412-145">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="e8412-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="e8412-146">Verplaatst naar de map Ongewenste E-mail als deze als spam is gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e8412-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="e8412-147">Verwijderd als phishing werd gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e8412-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="e8412-148">Als u wilt controleren of de berichten zijn verzonden, opent u de map **verzonden items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e8412-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="e8412-149">De invoegtoepassing voor het rapporteren van ongewenste E-mail installeren</span><span class="sxs-lookup"><span data-stu-id="e8412-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="e8412-150">U moet beheerdersmachtigingen hebben voor de computer waarop u de invoegtoepassing wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="e8412-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="e8412-151">Ga naar <https://www.microsoft.com/download/details.aspx?id=18275> en Download het juiste MSI-bestand voor uw versie van Office op een locatie die u kunt vinden:</span><span class="sxs-lookup"><span data-stu-id="e8412-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="e8412-152">**32-bits**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e8412-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="e8412-153">**64-bits**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e8412-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="e8412-154">Voor Outlook 2013 of hoger is het enige voorwaarden de Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="e8412-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="e8412-155">In Windows 10 installeert u .NET Framework 2,0 niet vanaf een download.</span><span class="sxs-lookup"><span data-stu-id="e8412-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="e8412-156">De invoegtoepassing voor het rapporteren van ongewenste E-mail installeren met de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="e8412-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="e8412-157">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="e8412-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="e8412-158">In Windows 10 controleert u of .NET Framework 2,0 is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e8412-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="e8412-159">Zie voor instructies [het artikel .NET Framework 3,5 inschakelen in het Configuratiescherm](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="e8412-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="e8412-160">Zoek het MSI-bestand dat u hebt gedownload en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="e8412-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="e8412-161">Klik op de pagina **Welkom bij Microsoft de instelling voor het rapporteren van de invoegtoepassing voor ongewenste e-mail** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8412-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="e8412-162">Bekijk de licentieovereenkomst, klik op **Ik ga akkoord met de voorwaarden in de licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8412-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="e8412-163">Wanneer de wizard is voltooid, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="e8412-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="e8412-164">Start Outlook.</span><span class="sxs-lookup"><span data-stu-id="e8412-164">Start Outlook.</span></span>

<span data-ttu-id="e8412-165">Zoek de knop **ongewenste e-mail** op het lint van Outlook.</span><span class="sxs-lookup"><span data-stu-id="e8412-165">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="e8412-166">U kunt nu ongewenste e-mailberichten voor Microsoft rapporteren door het e-mailbericht in uw postvak in te selecteren en te klikken op de knop **Ongewenste E-mail melden** .</span><span class="sxs-lookup"><span data-stu-id="e8412-166">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="e8412-167">Kies de pijl-omlaag naast **ongewenste e-mail** voor meer opties, zoals **rapporteren als phishing,** als u malafide e-mailberichten bij Microsoft wilt melden.</span><span class="sxs-lookup"><span data-stu-id="e8412-167">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="e8412-168">U kunt ook in de map Ongewenste e-mail de optie **geen ongewenste E-mail melden** als een e-mailadres verkeerd is aangemerkt als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="e8412-168">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="e8412-169">De invoegtoepassing voor het rapporteren van ongewenste E-mail installeren via de Stille modus</span><span class="sxs-lookup"><span data-stu-id="e8412-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="e8412-170">Sluit Outlook op uw computer.</span><span class="sxs-lookup"><span data-stu-id="e8412-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="e8412-171">In Windows 10 installeert u .NET Framework 2,0 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="e8412-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="e8412-172">Als u de invoegtoepassing wilt installeren zonder tussenkomst van de gebruiker, opent u een opdracht prompt en gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="e8412-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="e8412-173">`MaxMessageSelection` Hiermee geeft u het maximum aantal berichten op dat u voor één verzenden kunt selecteren.</span><span class="sxs-lookup"><span data-stu-id="e8412-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="e8412-174">Geldige waarden liggen tussen 1 en 50.</span><span class="sxs-lookup"><span data-stu-id="e8412-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="e8412-175">De standaardwaarde is 15.</span><span class="sxs-lookup"><span data-stu-id="e8412-175">The default value is 15.</span></span>

   - <span data-ttu-id="e8412-176">`BccEmailAddress` Hiermee geeft u meer BCC-geadresseerden op die een kopie ontvangen van alle gebruikers inzendingen.</span><span class="sxs-lookup"><span data-stu-id="e8412-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="e8412-177">De standaardwaarde is leeg (geen extra BCC-geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="e8412-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="e8412-178">In dit voorbeeld wordt de 64-bits versie van de invoegtoepassing geïnstalleerd vanaf het opgegeven pad, met de standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="e8412-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="e8412-179">In dit voorbeeld wordt de 32-bits versie van de invoegtoepassing in het opgegeven pad geïnstalleerd met de volgende aanvullende instellingen:</span><span class="sxs-lookup"><span data-stu-id="e8412-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="e8412-180">Er kunnen maximaal 20 berichten in één aanvraag worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="e8412-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="e8412-181">junkreports@contoso.com en hollyd@treyresearch.net ontvangen BCC-kopieën van alle inzendingen.</span><span class="sxs-lookup"><span data-stu-id="e8412-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e8412-182">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="e8412-182">How do you know this worked?</span></span>

<span data-ttu-id="e8412-183">Als u wilt controleren of de invoegtoepassing voor het rapporteren van ongewenste E-mail is geïnstalleerd, voert u de volgende stappen uit in Outlook:</span><span class="sxs-lookup"><span data-stu-id="e8412-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="e8412-184">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="e8412-184">Select the message or open the message.</span></span> <span data-ttu-id="e8412-185">Klik op het lint op het tabblad **Start** of **bericht** op **ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="e8412-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="e8412-186">**Rapporteren als ongewenste E-mail**</span><span class="sxs-lookup"><span data-stu-id="e8412-186">**Report as Junk**</span></span>
  - <span data-ttu-id="e8412-187">**Melden als phishing**</span><span class="sxs-lookup"><span data-stu-id="e8412-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="e8412-188">**Opties voor ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="e8412-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="e8412-189">**De Help voor ongewenste E-mail online rapporteren**</span><span class="sxs-lookup"><span data-stu-id="e8412-189">**Report Junk Online Help**</span></span>

  ![Ongewenste e-mail of malafide e-mail melden via het lint](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="e8412-191">Klik met de rechtermuisknop op het bericht, selecteer **ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="e8412-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="e8412-192">**Rapporteren als ongewenste E-mail**</span><span class="sxs-lookup"><span data-stu-id="e8412-192">**Report as Junk**</span></span>
  - <span data-ttu-id="e8412-193">**Melden als phishing**</span><span class="sxs-lookup"><span data-stu-id="e8412-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="e8412-194">**Opties voor ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="e8412-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="e8412-195">**De Help voor ongewenste E-mail online rapporteren**</span><span class="sxs-lookup"><span data-stu-id="e8412-195">**Report Junk Online Help**</span></span>

  ![Ongewenste e-mail of malafide e-mail melden met de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="e8412-197">Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="e8412-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="e8412-198">**Rapporteren als ongewenste E-mail**</span><span class="sxs-lookup"><span data-stu-id="e8412-198">**Report as Junk**</span></span>
  - <span data-ttu-id="e8412-199">**Melden als phishing**</span><span class="sxs-lookup"><span data-stu-id="e8412-199">**Report as Phishing**</span></span>

  ![Meerdere spam-en malafide e-mailberichten rapporteren met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="e8412-201">Ga als volgt te werk in de map **ongewenste e-mail** en controleer of de vorige opties voor het rapporteren van **Ongewenste E-mail** **geen ongewenste e-mail**zijn.</span><span class="sxs-lookup"><span data-stu-id="e8412-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Ongewenst of malafide e-mail melden via het lint in de map Ongewenste E-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Meld geen ongewenste e-mail of malafide e-mail van met de rechtermuisknop in de map Ongewenste E-mail.](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meld u niet af met de rechtermuisknop op de map Ongewenste e-mail of Meld u niet af met ongewenste e-mail.](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="e8412-205">De invoegtoepassing voor het rapporteren van ongewenste E-mail verwijderen</span><span class="sxs-lookup"><span data-stu-id="e8412-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="e8412-206">Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegtoepassing voor het rapporteren van ongewenste E-mail te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="e8412-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="e8412-207">**Configuratiescherm**: druk op de Windows-toets + R. Voer in het dialoogvenster **uitvoeren** dat wordt geopend, Enter `control appwiz.cpl` en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8412-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="e8412-208">Selecteer de **invoegtoepassing voor het rapporteren van ongewenste e-mail van Microsoft** in de lijst en klik op **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="e8412-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="e8412-209">**Windows-installatiepakket**: Zoek of download het juiste MSI-bestand en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="e8412-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="e8412-210">**32-bits**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e8412-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="e8412-211">**64-bits**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e8412-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="e8412-212">Selecteer in het dialoogvenster dat wordt weergegeven de optie **Microsoft-invoegtoepassing voor ongewenste E-mail verwijderen voor Outlook** en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8412-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="e8412-213">**Stille modus**: Zoek of download het juiste MSI-bestand.</span><span class="sxs-lookup"><span data-stu-id="e8412-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="e8412-214">In het venster met de opdracht prompt vervangt u \<PathToFile\> de locatie van het MSI-bestand en voert u een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="e8412-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="e8412-215">**32-bits**:</span><span class="sxs-lookup"><span data-stu-id="e8412-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="e8412-216">**64-bits**:</span><span class="sxs-lookup"><span data-stu-id="e8412-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="e8412-217">Wanneer u Outlook opent na de verwijdering, worden de opties ongewenste e-mail, geen ongewenste e-mail en malafide rapporten verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e8412-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="e8412-218">Problemen oplossen met de invoegtoepassing voor het rapporteren van ongewenste E-mail</span><span class="sxs-lookup"><span data-stu-id="e8412-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="e8412-219">Af en toe kunt u problemen ondervinden met Outlook na het toevoegen van de invoegtoepassing voor het rapporteren van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="e8412-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="e8412-220">In deze sectie worden problemen beschreven die u kunt ondervinden, samen met tips voor het oplossen van deze problemen.</span><span class="sxs-lookup"><span data-stu-id="e8412-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="e8412-221">Probleemoplossing voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="e8412-221">Troubleshooting for users</span></span>

<span data-ttu-id="e8412-222">U kunt een of meer van de volgende problemen ondervinden:</span><span class="sxs-lookup"><span data-stu-id="e8412-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="e8412-223">Er gebeurt niets wanneer u op **Ongewenste E-mail rapporteren** klikt</span><span class="sxs-lookup"><span data-stu-id="e8412-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="e8412-224">Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd</span><span class="sxs-lookup"><span data-stu-id="e8412-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="e8412-225">Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een niet-bezorgbaar antwoord</span><span class="sxs-lookup"><span data-stu-id="e8412-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="e8412-226">Voer de volgende stappen uit om dit probleem op te lossen:</span><span class="sxs-lookup"><span data-stu-id="e8412-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="e8412-227">Sluit Outlook af en start het programma opnieuw.</span><span class="sxs-lookup"><span data-stu-id="e8412-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="e8412-228">Maak een testbericht en verzend dit, en controleer of de geadresseerde het bericht heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="e8412-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="e8412-229">Als het probleem zich blijft voordoen, neemt u contact op met uw beheerder.</span><span class="sxs-lookup"><span data-stu-id="e8412-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="e8412-230">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere methoden die u kunt gebruiken om berichten naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="e8412-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="e8412-231">Probleemoplossing voor beheerders</span><span class="sxs-lookup"><span data-stu-id="e8412-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="e8412-232">Probleem: er wordt voortdurend een foutbericht weergegeven dat gebruikers vragen om contact op te nemen met hun systeembeheerder</span><span class="sxs-lookup"><span data-stu-id="e8412-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="e8412-233">Controleer of stel de `LoggingLevel` registersleutel in op de waarde ' uitgebreid '.</span><span class="sxs-lookup"><span data-stu-id="e8412-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="e8412-234">**32-bits versie van Outlook op 32-bits Windows**:</span><span class="sxs-lookup"><span data-stu-id="e8412-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="e8412-235">**32-bits versie van Outlook op 64-bits Windows**:</span><span class="sxs-lookup"><span data-stu-id="e8412-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="e8412-236">**64-bits Outlook**:</span><span class="sxs-lookup"><span data-stu-id="e8412-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="e8412-237">Start Outlook opnieuw en vraag gebruikers om opnieuw te rapporteren wanneer ze het foutbericht zien.</span><span class="sxs-lookup"><span data-stu-id="e8412-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="e8412-238">Verzamel de logboekinformatie op de volgende locatie:</span><span class="sxs-lookup"><span data-stu-id="e8412-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="e8412-239">Neem contact op met de technische ondersteuning van Exchange Online Protection en verstrek de logboekinformatie.</span><span class="sxs-lookup"><span data-stu-id="e8412-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="e8412-240">Probleem: gebruikers die hebben geselecteerd, geen bevestigingsprompt ontvangen wanneer ze berichten rapporteren, en nu willen ze de prompt weer terugvinden.</span><span class="sxs-lookup"><span data-stu-id="e8412-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="e8412-241">Maak de `ConfirmReportJunk` registersleutel met de waarde ' True ':</span><span class="sxs-lookup"><span data-stu-id="e8412-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="e8412-242">Start Outlook opnieuw.</span><span class="sxs-lookup"><span data-stu-id="e8412-242">Restart Outlook.</span></span>
