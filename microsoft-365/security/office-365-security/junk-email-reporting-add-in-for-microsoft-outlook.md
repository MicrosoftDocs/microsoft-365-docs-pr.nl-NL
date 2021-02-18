---
title: De invoegversie voor rapportage van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken
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
description: Informatie over het installeren en gebruiken van de invoegmap Microsoft -rapportage van ongewenste e-mail om spam, niet-spam en phishingberichten aan Microsoft te rapporteren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22a1364e8d7a1447bbcf518cc339a681c57a8af
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286619"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>De invoegversie voor rapportage van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Als u op dit moment de invoegapp Rapportage van ongewenste e-mail niet gebruikt, raden we u aan [de invoegapp](enable-the-report-message-add-in.md) Bericht rapporteren of De [invoegapp Phishing melden te](enable-the-report-phish-add-in.md) gebruiken. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

Met de invoegversie voor rapportage van ongewenste e-mail voor Microsoft Outlook kunnen gebruikers fout-positieven (goede e-mail die als spam is gemarkeerd), fout-negatieven (slechte e-mail toegestaan) en phishingberichten naar Microsoft verzenden. Als uw organisatie geen gebruik maakt van Exchange Online Protection (bijvoorbeeld on-premises Exchange- of e-mailservices anders dan Exchange Online), is het indienen van een rapport over ongewenste e-mail niet van invloed op uw spamfilter.

In dit onderwerp wordt uitgelegd hoe u de invoegaccount voor rapportage van ongewenste e-mail installeert en gebruikt.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie de sectie Over het rapporteren van ongewenste [e-mail](#install-the-junk-email-reporting-add-in) installeren verderf in dit artikel voor informatie over het installeren van de invoegmap Rapportage van ongewenste e-mail.

- De invoegversie voor rapportage van ongewenste e-mail werkt met de volgende versies van Outlook:

  - Outlook 2013 of hoger
  - Outlook inbegrepen in Microsoft 365-apps voor ondernemingen

- Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over het rapporteren van berichten [naar Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>De invoegmap Rapportage van ongewenste e-mail gebruiken om spam- en phishingberichten te melden

1. Voor berichten in het Postvak IN of een andere e-mailmap, met uitzondering van Ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:

   - Selecteer het bericht of open het bericht. Klik op  **het** tabblad Start **of** bericht op het lint op **Ongewenste** e-mail en selecteer Vervolgens Rapporteren als ongewenste e-mail of Rapporteren als **Phishing.**

     ![Ongewenste e-mail of phishing-e-mail melden via het lint](../../media/junk-email-reporting-ribbon.png)

   - Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste** e-mail en selecteer vervolgens Rapporteren als ongewenste e-mail **of** Melden als **Phishing.**

     ![Ongewenste e-mail of phishing-e-mail melden door met de rechtermuisknop te klikken](../../media/junk-email-reporting-right-click.png)

   - Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer Rapporteren **als** ongewenste e-mail of **Rapporteren als Phishing.**

     ![Meerdere ongewenste of phishing-e-mailberichten melden door met de rechtermuisknop te klikken](../../media/junk-email-reporting-right-click-multiple.png)

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.** Als u van gedachten verandert, klikt u **op Niet rapporteren.**

   ![Dialoogvenster Rapporteren als ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialoogvenster Voor het melden als phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:

   - Verplaatst naar de map Ongewenste e-mail als dit als spam is gerapporteerd.
   - Verwijderd als het als phishing is gerapporteerd.

   Als u wilt controleren of de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Gebruik de invoegmap Rapportage van ongewenste e-mail om niet-spam- en phishingberichten uit de map Ongewenste e-mail te rapporteren

1. Gebruik in de map Ongewenste e-mail een van de volgende methoden om fout-positieven of phishingberichten te melden:

   - Selecteer het bericht of open het bericht. Klik op **het** **tabblad Start** of bericht op het  lint op Geen ongewenste e-mail en selecteer Rapporteren als Geen ongewenste e-mail of Rapporteren **als Phishing.**

     ![Geen ongewenste e-mail of phishing-e-mail melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Klik met de rechtermuisknop op het bericht, klik op **Ongewenste** e-mail en selecteer Rapporteren als Geen ongewenste e-mail **of** Rapporteren als **Phishing.**

     ![Geen ongewenste e-mail of phishing-e-mail melden door met de rechtermuisknop in de map Ongewenste e-mail te klikken](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Selecteer meerdere berichten, klik met  de rechtermuisknop en selecteer Rapporteren als Geen ongewenste e-mail of **Melden als Phishing.**

     ![Meerdere berichten die geen ongewenste e-mail of phishingberichten zijn, melden door met de rechtermuisknop in de map Ongewenste e-mail te klikken](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.** Als u van gedachten verandert, klikt u **op Niet rapporteren.**

   ![Dialoogvenster Rapporteren als niet-ongewenste e-mail](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialoogvenster Voor het melden als phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:

   - Verplaatst naar de map Ongewenste e-mail als dit als spam is gerapporteerd.
   - Verwijderd als het als phishing is gerapporteerd.

   Als u wilt controleren of de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.

## <a name="install-the-junk-email-reporting-add-in"></a>De invoeg mailrapportage voor ongewenste e-mail installeren

- U moet beheerdersbevoegdheden hebben op de computer waarop u de invoeg toevoegt installeren.

- Ga naar en download het juiste MSI-bestand voor uw versie van Office naar een locatie <https://www.microsoft.com/download/details.aspx?id=18275> die u eenvoudig kunt vinden:

  - **32-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Voor Outlook 2013 of hoger is alleen Microsoft .NET Framework 2.0 vereist. In Windows 10 installeert u .NET Framework 2.0 niet via een download.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>De invoegverbinding voor rapportage van ongewenste e-mail installeren met de wizard Instellen

1. Sluit Outlook op uw computer.

2. Controleer in Windows 10 of .NET Framework 2.0 is ingeschakeld. Zie [.NET Framework 3.5 in het Configuratiescherm inschakelen voor instructies.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. Zoek het MSI-bestand dat u hebt gedownload en dubbelklik erop.

4. Klik op volgende op de pagina Installatie van **de invoeg** mailrapportage van Microsoft Welkom bij Microsoft voor het rapporteren van ongewenste **e-mail.**

5. Lees de gebruiksvoorwaarden, klik op Ik ga akkoord met de voorwaarden in de **licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende.**

6. Wanneer de wizard is voltooid, klikt u op **Voltooien.**

Start Outlook.

Zoek naar de **knop Ongewenste e-mail** op het lint van Outlook. U kunt ongewenste e-mailberichten nu rapporteren aan Microsoft door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop Ongewenste e-mail **rapporteren te** klikken.

Kies de pijl-omlaag naast **Ongewenste** e-mail voor meer opties, zoals Melden als **Phishing** als u phishing-e-mails wilt melden aan Microsoft. In de map Ongewenste e-mail  kunt u ook De optie Geen ongewenste e-mail rapporteren selecteren als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>De rapportagemodus voor ongewenste Add-In in de stille modus installeren

1. Sluit Outlook op uw computer.

2. Installeer in Windows 10 .NET Framework 2.0 door de volgende opdracht uit te voeren:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Als u de invoeg toepassing wilt installeren zonder tussenkomst van de gebruiker, opent u een opdrachtprompt en gebruikt u de volgende syntaxis:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` het maximum aantal berichten dat u kunt selecteren voor één inzending. Geldige waarden liggen tussen 1 en 50. De standaardwaarde is 15.

   - `BccEmailAddress` hiermee geeft u extra BCC-geadresseerden op die een kopie ontvangen van alle gebruikersinzendingen. De standaardwaarde is leeg (geen extra BCC-geadresseerden).

   In dit voorbeeld wordt de 64-bits versie van de invoegversie geïnstalleerd vanaf het opgegeven pad met de standaardinstellingen.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   In dit voorbeeld wordt de 32-bits versie van de invoegversie geïnstalleerd vanaf het opgegeven pad met de volgende aanvullende instellingen:

   - In één inzending kunnen maximaal 20 berichten worden geselecteerd.
   - junkreports@contoso.com en hollyd@treyresearch.net BCC-kopieën ontvangen van alle inzendingen.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de invoegversie voor rapportage van ongewenste e-mail hebt geïnstalleerd, gaat u op een van de volgende stappen in Outlook te werk:

- Selecteer het bericht of open het bericht. Klik op **het** **tabblad Start** of bericht op het lint op **Ongewenste** e-mail en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Melden als Phishing**
  - **Opties voor rapportage van ongewenste e-mail**
  - **Help bij Ongewenste e-mail melden**

  ![Ongewenste e-mail of phishing-e-mail melden via het lint](../../media/junk-email-reporting-ribbon.png)

- Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste** e-mail en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Melden als Phishing**
  - **Opties voor rapportage van ongewenste e-mail**
  - **Help bij Ongewenste e-mail melden**

  ![Ongewenste e-mail of phishing-e-mail melden door met de rechtermuisknop te klikken](../../media/junk-email-reporting-right-click.png)

- Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Melden als Phishing**

  ![Meerdere ongewenste of phishing-e-mailberichten melden door met de rechtermuisknop te klikken](../../media/junk-email-reporting-right-click-multiple.png)

- De vorige acties uitvoeren in de map  **Ongewenste e-mail** en controleren of de vorige opties voor het melden van ongewenste e-mail nu **Geen ongewenste e-mail zijn.**

  ![Geen ongewenste e-mail of phishing-e-mail melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Geen ongewenste e-mail of phishing-e-mail melden door met de rechtermuisknop in de map Ongewenste e-mail te klikken](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere berichten die geen ongewenste e-mail of phishingberichten zijn, melden door met de rechtermuisknop in de map Ongewenste e-mail te klikken](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>De invoegmap voor rapportage van ongewenste e-mail verwijderen

Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegversie voor rapportage van ongewenste e-mail te verwijderen:

- **Configuratiescherm:** druk op de Windows-toets + R. Typ in **het dialoogvenster** Uitvoeren dat wordt geopend en klik `control appwiz.cpl` op **OK.**

  Zoek en selecteer de microsoft-invoegmap voor rapportage van **ongewenste e-mail in** de lijst en klik vervolgens op **Verwijderen.**

- **Windows Installer-pakket:** zoek of download het juiste MSI-bestand en dubbelklik erop.

  - **32-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  Selecteer In het dialoogvenster dat wordt weergegeven, de **invoegversie Microsoft-invoegversie** voor rapportage van ongewenste e-mail voor Outlook verwijderen en klik vervolgens op **Volgende.**

- **Stille modus:** zoek of download het juiste MSI-bestand. Vervang in een opdrachtpromptvenster door de locatie van het MSI-bestand en \<PathToFile\> voer een van de volgende opdrachten uit:

  - **32-bits:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bits:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Wanneer u Outlook na het verwijderen opent, moeten de opties voor ongewenste e-mail, geen ongewenste e-mail en phishingberichten zijn verdwenen.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Problemen oplossen met de invoegmap Voor rapportage van ongewenste e-mail

Af en toe kan het zijn dat u problemen met Outlook hebt nadat u de invoegversie voor rapportage van ongewenste e-mail hebt toegevoegd. In deze sectie worden mogelijke problemen beschreven, samen met tips voor het oplossen van deze problemen.

### <a name="troubleshooting-for-users"></a>Probleemoplossing voor gebruikers

U kunt een of meer van de volgende problemen ervaren:

- Er gebeurt niets wanneer u op **Ongewenste e-mail rapporteren klikt**
- Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd
- Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een 'onbesleverbaar' antwoord

Ga als volgt te werk om dit probleem op te lossen:

1. Sluit Outlook en start het opnieuw.
2. Maak en verzend een testbericht en controleer of de geadresseerde het bericht heeft ontvangen.
3. Neem contact op met de beheerder als het probleem zich blijft voordoen.

Zie Berichten en bestanden rapporteren bij Microsoft voor andere methoden die u kunt gebruiken om berichten naar [Microsoft te verzenden.](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>Probleemoplossing voor beheerders

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Probleem: er wordt voortdurend een foutbericht weergegeven waarin gebruikers worden gevraagd contact op te nemen met hun systeembeheerder

1. Controleer of stel de `LoggingLevel` registersleutel in op de waarde 'Uitgebreid':

   - **32-bits Outlook op 32-bits Windows:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32-bits Outlook op 64-bits Windows:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64-bits Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Start Outlook opnieuw en vraag gebruikers om opnieuw te rapporteren wanneer ze het foutbericht zien.

3. Verzamel de logboekgegevens die op de volgende locatie zijn gevonden:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Neem contact op met de technische ondersteuning van Exchange Online Protection en geef de logboekgegevens door.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Probleem: Gebruikers die niet zijn geselecteerd, ontvangen geen bevestigingsprompt wanneer ze berichten rapporteren en willen de prompt weer terug hebben

1. Maak de `ConfirmReportJunk` registersleutel met de waarde 'Waar':

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Start Outlook opnieuw.
