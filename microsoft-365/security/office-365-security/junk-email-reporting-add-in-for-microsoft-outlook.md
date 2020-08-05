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
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>De invoegtoepassing Ongewenste e-mailrapportage voor Microsoft Outlook installeren en gebruiken

> [!NOTE]
> Als u momenteel de invoegtoepassing Ongewenste e-mailrapportage niet gebruikt, raden we u in plaats daarvan de [invoegtoepassing Rapportbericht aan.](enable-the-report-message-add-in.md) Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

Met de add-invoeging voor ongewenste e-mailrapportage voor Microsoft Outlook kunnen gebruikers valse positieven (goede e-mail gemarkeerd als spam), valse negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Microsoft. Als uw organisatie geen Exchange Online Protection gebruikt (bijvoorbeeld on-premises Exchange of andere e-mailservices dan Exchange Online), heeft uw indiening van ongewenste e-mailverslagen geen invloed op uw spamfiltering.

In dit onderwerp wordt uitgelegd hoe u de invoegtoepassing Ongewenste e-mailrapportage installeert en gebruikt.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie de [invoegtoepassing Ongewenste e-mailrapportage](#install-the-junk-email-reporting-add-in) installeren in dit onderwerp om de invoegtoepassing Ongewenste e-mailrapportage te installeren.

- De invoegtoepassing Rapportage voor ongewenste e-mail werkt met de volgende versies van Outlook:

  - Outlook 2013 of hoger
  - Outlook inbegrepen bij Microsoft 365 Apps for Enterprise

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>De invoegtoepassing Ongewenste e-mailrapportage gebruiken om spam- en phishingberichten te melden

1. Voor berichten in het Postvak IN of een andere e-mailmap, behalve ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:

   - Selecteer het bericht of open het bericht. Klik op het tabblad **Start** of **bericht** op het lint op **Ongewenste e-mail**en selecteer **Rapporteren als ongewenste e-mail** of **rapport als phishing**.

     ![E-mail met ongewenste e-mail of phishing melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

   - Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail**en selecteer **Rapporteren als ongewenste e-mail** of rapport als **phishing**.

     ![E-mail met de rechtermuisknop melden](../../media/junk-email-reporting-right-click.png)

   - Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als ongewenste e-mail** of **rapport als phishing**.

     ![Meerdere ongewenste e-mailberichten melden met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport**. Als u van gedachten verandert, klikt u op **Niet rapporteren**.

   ![Dialoogvenster Rapporteren als ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialoogvenster rapporteren als phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:

   - Verplaatst naar de map Ongewenste e-mail als deze als spam is gerapporteerd.
   - Verwijderd als het werd gemeld als phishing.
   
   Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de verzonden berichten weer te geven.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>De invoegtoepassing Ongewenste e-mailrapportage gebruiken om niet-spam- en phishingberichten te rapporteren vanuit de map Ongewenste e-mail

1. Gebruik in de map Ongewenste e-mail een van de volgende methoden om spamalmerk-positieven of phishingberichten te melden:

   - Selecteer het bericht of open het bericht. Klik op het tabblad **Start** of **bericht** op het lint op **Niet ongewenste e-mail**en selecteer Rapporteren als **niet-ongewenste e-mail** of **rapport als phishing**.

     ![Geen ongewenste e-mail of phishing-e-mail melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Klik met de rechtermuisknop op het bericht, klik op **Ongewenste e-mail**en selecteer **Rapporteren als niet-ongewenste e-mail** of **rapport als phishing**.

     ![Niet ongewenste e-mail of phishing-e-mail melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **Rapporteren als niet-ongewenste e-mail** of **rapport als phishing**.

     ![Meerdere niet-ongewenste e-mailberichten of phishing-e-mailberichten melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport**. Als u van gedachten verandert, klikt u op **Niet rapporteren**.

   ![Dialoogvenster Rapporteren als niet-ongewenste e-mail](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialoogvenster rapporteren als phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:

   - Verplaatst naar de map Ongewenste e-mail als deze als spam is gerapporteerd.
   - Verwijderd als het werd gemeld als phishing.

   Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de verzonden berichten weer te geven.

## <a name="install-the-junk-email-reporting-add-in"></a>De invoegtoepassing Ongewenste e-mailrapportage installeren

- U moet beheerdersbevoegdheden hebben op de computer waar u de invoegtoepassing installeert.

- Ga naar <https://www.microsoft.com/download/details.aspx?id=18275> en download het juiste .msi-bestand voor uw versie van Office naar een locatie die gemakkelijk te vinden is:

  - **32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Voor Outlook 2013 of hoger is de enige vereiste de Microsoft .NET Framework 2.0. In Windows 10 installeert u de .NET Framework 2.0 niet vanaf een download.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>De invoegtoepassing Rapportage voor ongewenste e-mail installeren met de wizard Setup

1. Sluit Outlook op uw computer.

2. Controleer in Windows 10 of de .NET Framework 2.0 is ingeschakeld. Zie Het [.NET Framework 3.5 inschakelen in het Configuratiescherm](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)voor instructies.

3. Zoek het .msi-bestand dat je hebt gedownload en dubbelklik erop.

4. Klik op de pagina **Invoegtoepassingsrapportage voor ongewenste e-mailrapportage** op **Volgende**.

5. Controleer de licentieovereenkomst, klik op **Ik accepteer de voorwaarden in de licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende**.

6. Wanneer de wizard is voltooid, klikt u op **Voltooien**.

Start Outlook.

Zoek naar de knop **Ongewenste e-mail** op het Outlook-lint. U nu ongewenste e-mailberichten aan Microsoft rapporteren door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste e-mailrapport** te klikken.

Kies de pijl-omlaag naast **Ongewenste e-mail** voor meer opties, zoals **Rapporteren als phishing** als u phishing-scam-e-mails wilt melden aan Microsoft. In uw map met ongewenste e-mail u ook **ongewenste e-mail** melden als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>De invoegtoepassing Ongewenste e-mailrapportage installeren met de stille modus

1. Sluit Outlook op uw computer.

2. Installeer in Windows 10 de .NET Framework 2.0 door de volgende opdracht uit te voeren:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Als u de invoegtoepassing wilt installeren zonder interactie van de gebruiker, opent u een opdrachtprompt en gebruikt u de volgende syntaxis:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection`hiermee geeft u het maximum aantal berichten op dat u selecteren voor één inzending. Geldige waarden zijn van 1 tot 50. De standaardwaarde is 15.

   - `BccEmailAddress`geeft extra BCC-ontvangers op die een kopie van alle gebruikersinzendingen ontvangen. De standaardwaarde is leeg (geen extra BCC-ontvangers).

   In dit voorbeeld wordt de 64-bits versie van de invoegtoepassing vanaf het opgegeven pad met de standaardinstellingen geïnstalleerd.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   In dit voorbeeld wordt de 32-bits versie van de invoegtoepassing vanaf het opgegeven pad met de volgende extra instellingen geïnstalleerd:

   - Maximaal 20 berichten kunnen in één inzending worden geselecteerd.
   - junkreports@contoso.com en hollyd@treyresearch.net ontvangen BCC kopieën van alle inzendingen.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de invoegtoepassing Voor rapportage voor ongewenste e-mail hebt geïnstalleerd, voert u een van de volgende stappen uit in Outlook:

- Selecteer het bericht of open het bericht. Klik op het tabblad **Start** of **bericht** op het lint op **Ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Rapporteren als phishing**
  - **Opties voor ongewenste rapportage**
  - **Help voor ongewenste e-mail melden**

  ![E-mail met ongewenste e-mail of phishing melden vanaf het lint](../../media/junk-email-reporting-ribbon.png)

- Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail**en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Rapporteren als phishing**
  - **Opties voor ongewenste rapportage**
  - **Help voor ongewenste e-mail melden**

  ![E-mail met de rechtermuisknop melden](../../media/junk-email-reporting-right-click.png)

- Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Rapporteren als phishing**

  ![Meerdere ongewenste e-mailberichten melden met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- Doe de vorige acties in de map **Ongewenste e-mail** en controleer of de vorige opties **voor ongewenste e-mail** nu **geen ongewenste e-mail**zijn.

  ![Geen ongewenste e-mail of phishing-e-mail melden vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Niet ongewenste e-mail of phishing-e-mail melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere niet-ongewenste e-mailberichten of phishing-e-mailberichten melden vanuit de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>De invoegtoepassing Rapportage voor ongewenste e-mail verwijderen

Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegtoepassing Voor de rapportage voor ongewenste e-mail te verwijderen:

- **Configuratiescherm**: Druk op de Windows-toets + R. Voer in het dialoogvenster **Uitvoeren** dat wordt geopend, in `control appwiz.cpl` en klik op **OK**.

  Zoek en selecteer **Microsoft Junk Email Reporting Add-in** in de lijst en klik vervolgens op **Verwijderen**.

- **Windows Installer-pakket**: zoek of download het juiste .msi-bestand en dubbelklik erop.

  - **32-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bits**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  Selecteer in het dialoogvenster dat wordt weergegeven de optie **Microsoft-rapportage voor ongewenste e-mail voor Outlook verwijderen** en klik vervolgens op **Volgende**.

- **Silent Mode**: Zoek of download het juiste .msi-bestand. Vervang in een opdrachtpromptvenster \<PathToFile\> de locatie van het .msi-bestand en voer een van de volgende opdrachten uit:

  - **32-bits**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bits**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Wanneer u Outlook opent na het verwijderen, moeten de opties voor ongewenste e-mail, niet ongewenste e-mail en phishing-rapportage zijn verdwenen.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Problemen met de invoegtoepassing Ongewenste e-mailrapportage oplossen

Soms u problemen ondervinden met Outlook nadat u de invoegtoepassing Voor de rapportage voor ongewenste e-mail hebt toegevoegd. In deze sectie worden problemen beschreven die u mogelijk tegenkomt, samen met tips voor het oplossen van deze problemen.

### <a name="troubleshooting-for-users"></a>Probleemoplossing voor gebruikers

U ondervindt een of meer van de volgende problemen:

- Er gebeurt niets wanneer u op **Ongewenste e-mail rapporteren klikt**
- Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd
- Gemelde ongewenste e-mail kan niet worden bezorgd vanwege een "onbestelbaar" antwoord

Ga als volgt te werk om dit probleem op te lossen:

1. Outlook sluiten en opnieuw starten.
2. Maak en verzend een testbericht en controleer of de ontvanger het bericht heeft ontvangen.
3. Als het probleem blijft bestaan, neemt u contact op met uw beheerder.

Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)andere methoden die u gebruiken om berichten naar Microsoft in te dienen.

### <a name="troubleshooting-for-admins"></a>Probleemoplossing voor beheerders

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Probleem: er verschijnt voortdurend een foutbericht waarin gebruikers wordt gevraagd contact op te nemen met hun systeembeheerder

1. Controleer of stel de registersleutel in `LoggingLevel` op de waarde "Verbose":

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

   - **64-bits Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Start Outlook opnieuw op en vraag gebruikers om verslag uit te brengen wanneer ze het foutbericht zien.

3. Verzamel de loggegevens die op de volgende locatie zijn gevonden:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Neem contact op met de technische ondersteuning van Exchange Online Protection en geef ze de loggegevens.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Probleem: gebruikers die zijn geselecteerd om geen bevestigingsprompt te ontvangen wanneer ze berichten rapporteren en willen nu de prompt terug

1. Maak de `ConfirmReportJunk` registersleutel met de waarde 'Waar':

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Start Outlook opnieuw.
