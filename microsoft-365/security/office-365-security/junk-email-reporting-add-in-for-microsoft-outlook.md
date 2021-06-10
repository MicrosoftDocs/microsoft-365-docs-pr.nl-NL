---
title: Installeer en gebruik de invoegmap Voor het rapporteren van ongewenste e-mail voor Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Meer informatie over het installeren en gebruiken van de microsoft-invoegvoeging voor het rapporteren van ongewenste e-mail om spam, niet-spam en phishingberichten bij Microsoft te melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204237"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="8ccbf-103">Installeer en gebruik de invoegmap Voor het rapporteren van ongewenste e-mail voor Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="8ccbf-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8ccbf-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-104">**Applies to**</span></span>
- [<span data-ttu-id="8ccbf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8ccbf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8ccbf-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8ccbf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8ccbf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ccbf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="8ccbf-108">Als u momenteel geen gebruik maakt van de invoegapp [](enable-the-report-message-add-in.md) Ongewenste e-mailrapportage, raden we u de invoegvoeging Bericht melden of de invoeging [Phishing melden aan.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="8ccbf-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="8ccbf-109">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8ccbf-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="8ccbf-110">Met de invoegvoegmap Voor rapportage van ongewenste e-mail voor Microsoft Outlook kunnen gebruikers fout-positieven (goede e-mail die is gemarkeerd als spam), fout-negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="8ccbf-111">Als uw organisatie geen gebruik maakt van Exchange Online Protection (bijvoorbeeld on-premises Exchange- of e-mailservices anders dan Exchange Online), heeft het indienen van ongewenste e-mail geen invloed op uw spamfilters.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="8ccbf-112">In dit onderwerp wordt uitgelegd hoe u de invoegvoegmap Voor het rapporteren van ongewenste e-mail installeert en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8ccbf-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8ccbf-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8ccbf-114">Als u de invoegsnede Voor het rapporteren van ongewenste e-mail wilt installeren, gaat u naar de sectie De invoeging voor ongewenste [e-mailrapportage](#install-the-junk-email-reporting-add-in) installeren verder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="8ccbf-115">De invoegversie voor rapportage van ongewenste e-mail werkt met de volgende versies van Outlook:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="8ccbf-116">Outlook 2013 of hoger</span><span class="sxs-lookup"><span data-stu-id="8ccbf-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="8ccbf-117">Outlook inbegrepen bij Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8ccbf-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="8ccbf-118">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8ccbf-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="8ccbf-119">De invoeging Voor het rapporteren van ongewenste e-mail gebruiken om spam- en phishingberichten te melden</span><span class="sxs-lookup"><span data-stu-id="8ccbf-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="8ccbf-120">Voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="8ccbf-121">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-121">Select the message or open the message.</span></span> <span data-ttu-id="8ccbf-122">Klik op **het tabblad** Start **of** Bericht op het lint op **Ongewenste e-mail** en selecteer **rapport als** ongewenste e-mail of Rapport **als phishing.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="8ccbf-124">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail** en selecteer **rapport als ongewenste** e-mail of Rapport als **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Meld ongewenste e-mail of phishing-e-mail met de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="8ccbf-126">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **rapport als ongewenste** e-mail of Rapport als **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Meerdere ongewenste e-mailberichten of phishing-e-mailberichten rapporteren met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="8ccbf-128">Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="8ccbf-129">Als u van gedachten verandert, klikt **u op Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-129">If you change your mind, click **Don't Report**.</span></span>

   ![Dialoogvenster Rapport als ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Rapport als phishingdialoogvenster](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="8ccbf-132">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="8ccbf-133">Verplaatst naar de map Ongewenste e-mail als deze is gerapporteerd als spam.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="8ccbf-134">Verwijderd als dit is gerapporteerd als phishing.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="8ccbf-135">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="8ccbf-136">Gebruik de invoegmap Ongewenste e-mailrapportage om niet-spam- en phishingberichten uit de map Ongewenste e-mail te rapporteren</span><span class="sxs-lookup"><span data-stu-id="8ccbf-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="8ccbf-137">Gebruik in de map Ongewenste e-mail een van de volgende methoden om ongewenste e-mail of phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="8ccbf-138">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-138">Select the message or open the message.</span></span> <span data-ttu-id="8ccbf-139">Klik op **het tabblad** **Start** of Bericht op het lint op Geen ongewenste **e-mail** en selecteer **rapport als geen** ongewenste e-mail of Rapport als **phishing.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Geen ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="8ccbf-141">Klik met de rechtermuisknop op het bericht, klik **op Ongewenste e-mail** en selecteer **rapport als geen** ongewenste e-mail of Rapport als **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapport geen ongewenste e-mail of phishing-e-mail van klik met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="8ccbf-143">Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **rapport als geen** ongewenste e-mail of Rapport als **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Meerdere niet-ongewenste e-mailberichten of phishingberichten rapporteren door met de rechtermuisknop te klikken in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="8ccbf-145">Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="8ccbf-146">Als u van gedachten verandert, klikt **u op Niet rapporteren.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-146">If you change your mind, click **Don't Report**.</span></span>

   ![Dialoogvenster Rapport als geen ongewenste e-mail](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Rapport als phishingdialoogvenster](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="8ccbf-149">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="8ccbf-150">Verplaatst naar de map Ongewenste e-mail als deze is gerapporteerd als spam.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="8ccbf-151">Verwijderd als dit is gerapporteerd als phishing.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="8ccbf-152">Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="8ccbf-153">De invoegmap Voor het rapporteren van ongewenste e-mail installeren</span><span class="sxs-lookup"><span data-stu-id="8ccbf-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="8ccbf-154">U moet beheerdersbevoegdheden hebben op de computer waarop u de invoeging installeert.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="8ccbf-155">Ga naar en download het .msi bestand voor uw versie van Office naar een locatie die <https://www.microsoft.com/download/details.aspx?id=18275> u gemakkelijk kunt vinden:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="8ccbf-156">**32-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8ccbf-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="8ccbf-157">**64-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8ccbf-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="8ccbf-158">Voor Outlook 2013 of hoger is de microsoft-.NET Framework 2.0 de enige vereiste.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="8ccbf-159">In Windows 10 installeert u de .NET Framework 2.0 niet via een download.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="8ccbf-160">De invoeginstallatie voor rapportage van ongewenste e-mail installeren met behulp van de wizard Instellen</span><span class="sxs-lookup"><span data-stu-id="8ccbf-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="8ccbf-161">Sluit op uw computer de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="8ccbf-162">Controleer Windows 10 de .NET Framework 2.0 is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="8ccbf-163">Zie De .NET Framework [3.5 in het Configuratiescherm inschakelen](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="8ccbf-164">Zoek het .msi bestand dat u hebt gedownload en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="8ccbf-165">Klik op **de pagina Welcome to Microsoft Junk Email Reporting Add-in Setup** op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="8ccbf-166">Bekijk de licentieovereenkomst, klik op Ik accepteer de voorwaarden in de **licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="8ccbf-167">Wanneer de wizard is voltooid, klikt u op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="8ccbf-168">Start Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-168">Start Outlook.</span></span>

<span data-ttu-id="8ccbf-169">Zoek naar de **knop Ongewenste e-mail** op Outlook lint.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-169">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="8ccbf-170">U kunt nu ongewenste e-mailberichten rapporteren aan Microsoft door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste e-mail rapporteren te** klikken.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-170">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="8ccbf-171">Kies de pijl-omlaag naast **Ongewenste** e-mail voor meer opties, zoals Rapporteren als **Phishing** als u phishingberichten wilt melden bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-171">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="8ccbf-172">In de map ongewenste e-mail kunt u ook Rapporteren geen ongewenste e-mail **selecteren** als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-172">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="8ccbf-173">De meldingsmodus voor ongewenste Add-In installeren met behulp van de stille modus</span><span class="sxs-lookup"><span data-stu-id="8ccbf-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="8ccbf-174">Sluit op uw computer de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="8ccbf-175">Installeer Windows 10 2.0 .NET Framework 2.0 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="8ccbf-176">Open een opdrachtprompt en gebruik de volgende syntaxis om de invoegactie te installeren zonder interactie met de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="8ccbf-177">`MaxMessageSelection` geeft het maximum aantal berichten op dat u kunt selecteren voor één inzending.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="8ccbf-178">Geldige waarden zijn 1 tot 50.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="8ccbf-179">De standaardwaarde is 15.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-179">The default value is 15.</span></span>

   - <span data-ttu-id="8ccbf-180">`BccEmailAddress` geeft extra BCC-geadresseerden op die een kopie van alle gebruikersinzendingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="8ccbf-181">De standaardwaarde is leeg (geen extra BCC-geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="8ccbf-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="8ccbf-182">In dit voorbeeld wordt de 64-bits versie van de invoegversie geïnstalleerd vanaf het opgegeven pad met de standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="8ccbf-183">In dit voorbeeld wordt de 32-bits versie van de invoegversie geïnstalleerd vanaf het opgegeven pad met de volgende aanvullende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="8ccbf-184">Er kunnen maximaal 20 berichten worden geselecteerd in één inzending.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="8ccbf-185">junkreports@contoso.com en hollyd@treyresearch.net BCC-kopieën van alle inzendingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8ccbf-186">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="8ccbf-186">How do you know this worked?</span></span>

<span data-ttu-id="8ccbf-187">Ga als volgt te werk als u wilt controleren of u de invoegvoegmap Voor rapportage van ongewenste e-mail hebt Outlook:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="8ccbf-188">Selecteer het bericht of open het bericht.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-188">Select the message or open the message.</span></span> <span data-ttu-id="8ccbf-189">Klik op **het tabblad** Start **of** Bericht op het lint op **Ongewenste e-mail** en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="8ccbf-190">**Rapporteren als ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-190">**Report as Junk**</span></span>
  - <span data-ttu-id="8ccbf-191">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="8ccbf-192">**Opties voor het rapporteren van ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="8ccbf-193">**Help bij ongewenste e-mail melden**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-193">**Report Junk Online Help**</span></span>

  ![Ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="8ccbf-195">Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail** en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="8ccbf-196">**Rapporteren als ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-196">**Report as Junk**</span></span>
  - <span data-ttu-id="8ccbf-197">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="8ccbf-198">**Opties voor het rapporteren van ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="8ccbf-199">**Help bij ongewenste e-mail melden**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-199">**Report Junk Online Help**</span></span>

  ![Meld ongewenste e-mail of phishing-e-mail met de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="8ccbf-201">Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="8ccbf-202">**Rapporteren als ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-202">**Report as Junk**</span></span>
  - <span data-ttu-id="8ccbf-203">**Rapporteren als Phishing**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-203">**Report as Phishing**</span></span>

  ![Meerdere ongewenste e-mailberichten of phishing-e-mailberichten rapporteren met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="8ccbf-205">Doe de vorige acties in de map  **Ongewenste e-mail** en controleer of de vorige opties voor het rapporteren van ongewenste e-mail nu **Geen ongewenste e-mail zijn.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Geen ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapport geen ongewenste e-mail of phishing-e-mail van klik met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere niet-ongewenste e-mailberichten of phishingberichten rapporteren door met de rechtermuisknop te klikken in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="8ccbf-209">De invoegvoegmap Voor het rapporteren van ongewenste e-mail verwijderen</span><span class="sxs-lookup"><span data-stu-id="8ccbf-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="8ccbf-210">Nadat u de Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegvoegprocedure voor het rapporteren van ongewenste e-mail te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="8ccbf-211">**Configuratiescherm:** Druk op Windows +R. Typ in **het dialoogvenster** Uitvoeren dat wordt geopend en klik vervolgens `control appwiz.cpl` op **OK.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="8ccbf-212">Zoek en selecteer **Microsoft Junk Email Reporting Add-in in** de lijst en klik vervolgens op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="8ccbf-213">**Windows Installer-pakket:** Zoek of download het juiste .msi bestand en dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="8ccbf-214">**32-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8ccbf-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="8ccbf-215">**64-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8ccbf-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="8ccbf-216">Selecteer in het dialoogvenster dat wordt weergegeven de optie **Microsoft Junk Email Reporting Add-in** for Outlook en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="8ccbf-217">**Stille modus:** zoek of download het juiste .msi bestand.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="8ccbf-218">Vervang in een opdrachtpromptvenster door de locatie van het .msi bestand en voer een van de \<PathToFile\> volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="8ccbf-219">**32-bits:**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="8ccbf-220">**64-bits:**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="8ccbf-221">Wanneer u de Outlook na het verwijderen, moeten de opties voor ongewenste e-mail, geen ongewenste e-mail en phishingrapportage zijn verdwenen.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="8ccbf-222">Problemen met de invoegmap Voor het rapporteren van ongewenste e-mail oplossen</span><span class="sxs-lookup"><span data-stu-id="8ccbf-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="8ccbf-223">Af en toe kunt u problemen met Outlook na het toevoegen van de invoeging voor rapportage van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="8ccbf-224">In deze sectie worden problemen beschreven die u mogelijk ondervindt, samen met tips voor het oplossen van deze problemen.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="8ccbf-225">Probleemoplossing voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="8ccbf-225">Troubleshooting for users</span></span>

<span data-ttu-id="8ccbf-226">U ervaart een of meer van de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="8ccbf-227">Er gebeurt niets wanneer u op **Ongewenste e-mail rapporteren klikt**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="8ccbf-228">Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd</span><span class="sxs-lookup"><span data-stu-id="8ccbf-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="8ccbf-229">Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een antwoord dat niet kan worden bezorgd</span><span class="sxs-lookup"><span data-stu-id="8ccbf-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="8ccbf-230">Ga als volgt te werk om dit probleem op te lossen:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="8ccbf-231">Sluit de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="8ccbf-232">Maak en verzend een testbericht en controleer of de geadresseerde het bericht heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="8ccbf-233">Als het probleem zich blijft voordoen, neem dan contact op met de beheerder.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="8ccbf-234">Zie Berichten en bestanden rapporteren bij Microsoft voor andere methoden die u kunt gebruiken om berichten bij Microsoft [in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8ccbf-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="8ccbf-235">Probleemoplossing voor beheerders</span><span class="sxs-lookup"><span data-stu-id="8ccbf-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="8ccbf-236">Probleem: er wordt voortdurend een foutbericht weergegeven waarin gebruikers worden gevraagd contact op te nemen met de systeembeheerder</span><span class="sxs-lookup"><span data-stu-id="8ccbf-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="8ccbf-237">Controleer of stel de `LoggingLevel` registersleutel in op de waarde 'Verbose':</span><span class="sxs-lookup"><span data-stu-id="8ccbf-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="8ccbf-238">**32-bits Outlook 32-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="8ccbf-239">**32-bits Outlook 64-bits Windows:**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="8ccbf-240">**64-bits Outlook:**</span><span class="sxs-lookup"><span data-stu-id="8ccbf-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="8ccbf-241">Start Outlook en vraag gebruikers om het rapport terug te geven wanneer ze het foutbericht zien.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="8ccbf-242">Verzamel de logboekgegevens die op de volgende locatie zijn gevonden:</span><span class="sxs-lookup"><span data-stu-id="8ccbf-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="8ccbf-243">Neem contact Exchange Online Protection technische ondersteuning op en geef ze de logboekgegevens.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="8ccbf-244">Probleem: Gebruikers hebben geselecteerd om geen bevestigingsprompt te ontvangen wanneer ze berichten rapporteren, en nu willen ze de prompt terug</span><span class="sxs-lookup"><span data-stu-id="8ccbf-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="8ccbf-245">Maak de `ConfirmReportJunk` registersleutel met de waarde 'Waar':</span><span class="sxs-lookup"><span data-stu-id="8ccbf-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="8ccbf-246">Start Outlook opnieuw.</span><span class="sxs-lookup"><span data-stu-id="8ccbf-246">Restart Outlook.</span></span>