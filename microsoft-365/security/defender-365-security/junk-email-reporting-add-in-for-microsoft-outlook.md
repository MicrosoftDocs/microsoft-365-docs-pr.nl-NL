---
title: De invoegversie voor het rapporteren van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken
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
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060069"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>De invoegversie voor het rapporteren van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Als u momenteel geen gebruik maakt van de invoegapp [](enable-the-report-message-add-in.md) Ongewenste e-mailrapportage, raden we u de invoegvoeging Bericht melden of de invoeging [Phishing melden aan.](enable-the-report-phish-add-in.md) Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

Met de invoegversie voor rapportage van ongewenste e-mail voor Microsoft Outlook kunnen gebruikers fout-positieven (goede e-mail die is gemarkeerd als spam), onwaar negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Microsoft. Als uw organisatie geen gebruik maakt van Exchange Online Protection (bijvoorbeeld on-premises Exchange- of e-mailservices anders dan Exchange Online), heeft het indienen van een rapport over ongewenste e-mail geen invloed op uw spamfilters.

In dit onderwerp wordt uitgelegd hoe u de invoegvoegmap Voor het rapporteren van ongewenste e-mail installeert en gebruikt.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u de invoegsnede Voor het rapporteren van ongewenste e-mail wilt installeren, gaat u naar de sectie De invoeging voor ongewenste [e-mailrapportage](#install-the-junk-email-reporting-add-in) installeren verder in dit artikel.

- De invoegversie voor rapportage van ongewenste e-mail werkt met de volgende versies van Outlook:

  - Outlook 2013 of hoger
  - Outlook inbegrepen bij Microsoft 365 Apps voor bedrijven

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>De invoeging Voor het rapporteren van ongewenste e-mail gebruiken om spam- en phishingberichten te melden

1. Voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:

   - Selecteer het bericht of open het bericht. Klik op **het tabblad** Start **of** Bericht op het lint op **Ongewenste e-mail** en selecteer **rapport als** ongewenste e-mail of Rapport **als phishing.**

     ![Ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint](../../media/junk-email-reporting-ribbon.png)

   - Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail** en selecteer **rapport als ongewenste** e-mail of Rapport als **Phishing.**

     ![Meld ongewenste e-mail of phishing-e-mail met de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

   - Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **rapport als ongewenste** e-mail of Rapport als **Phishing.**

     ![Meerdere ongewenste e-mailberichten of phishing-e-mailberichten rapporteren met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.** Als u van gedachten verandert, klikt **u op Niet rapporteren.**

   ![Dialoogvenster Rapport als ongewenste e-mail](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Rapport als phishingdialoogvenster](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:

   - Verplaatst naar de map Ongewenste e-mail als deze is gerapporteerd als spam.
   - Verwijderd als dit is gerapporteerd als phishing.

   Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Gebruik de invoegmap Ongewenste e-mailrapportage om niet-spam- en phishingberichten uit de map Ongewenste e-mail te rapporteren

1. Gebruik in de map Ongewenste e-mail een van de volgende methoden om ongewenste e-mail of phishingberichten te melden:

   - Selecteer het bericht of open het bericht. Klik op **het tabblad** **Start** of Bericht op het lint op Geen ongewenste **e-mail** en selecteer **rapport als geen** ongewenste e-mail of Rapport als **phishing.**

     ![Geen ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Klik met de rechtermuisknop op het bericht, klik **op Ongewenste e-mail** en selecteer **rapport als geen** ongewenste e-mail of Rapport als **Phishing.**

     ![Rapport geen ongewenste e-mail of phishing-e-mail van klik met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Selecteer meerdere berichten, klik met de rechtermuisknop en selecteer **rapport als geen** ongewenste e-mail of Rapport als **Phishing.**

     ![Meerdere niet-ongewenste e-mailberichten of phishingberichten rapporteren door met de rechtermuisknop te klikken in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.** Als u van gedachten verandert, klikt **u op Niet rapporteren.**

   ![Dialoogvenster Rapport als geen ongewenste e-mail](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Rapport als phishingdialoogvenster](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:

   - Verplaatst naar de map Ongewenste e-mail als deze is gerapporteerd als spam.
   - Verwijderd als dit is gerapporteerd als phishing.

   Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.

## <a name="install-the-junk-email-reporting-add-in"></a>De invoegmap Voor het rapporteren van ongewenste e-mail installeren

- U moet beheerdersbevoegdheden hebben op de computer waarop u de invoeging installeert.

- Ga naar <https://www.microsoft.com/download/details.aspx?id=18275> en download het juiste MSI-bestand voor uw versie van Office naar een locatie die gemakkelijk te vinden is:

  - **32-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Voor Outlook 2013 of hoger is microsoft .NET Framework 2.0 de enige vereiste. In Windows 10 installeert u de .NET Framework 2.0 niet via een download.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>De invoeginstallatie voor rapportage van ongewenste e-mail installeren met behulp van de wizard Instellen

1. Sluit Outlook op uw computer.

2. Controleer in Windows 10 of .NET Framework 2.0 is ingeschakeld. Zie Het [.NET Framework 3.5 in het Configuratiescherm inschakelen](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)voor instructies.

3. Zoek het MSI-bestand dat u hebt gedownload en dubbelklik erop.

4. Klik op **de pagina Welcome to Microsoft Junk Email Reporting Add-in Setup** op **Volgende.**

5. Bekijk de licentieovereenkomst, klik op Ik accepteer de voorwaarden in de **licentieovereenkomst** als u akkoord gaat met de voorwaarden en klik vervolgens op **Volgende**.

6. Wanneer de wizard is voltooid, klikt u op **Voltooien.**

Start Outlook.

Zoek naar de **knop Ongewenste e-mail** op het Lint van Outlook. U kunt nu ongewenste e-mailberichten rapporteren aan Microsoft door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste e-mail rapporteren te** klikken.

Kies de pijl-omlaag naast **Ongewenste** e-mail voor meer opties, zoals Rapporteren als **Phishing** als u phishingberichten wilt melden bij Microsoft. In de map ongewenste e-mail kunt u ook Rapporteren geen ongewenste e-mail **selecteren** als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>De meldingsmodus voor ongewenste Add-In installeren met behulp van de stille modus

1. Sluit Outlook op uw computer.

2. Installeer in Windows 10 de .NET Framework 2.0 door de volgende opdracht uit te voeren:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Open een opdrachtprompt en gebruik de volgende syntaxis om de invoegactie te installeren zonder interactie met de gebruiker:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` geeft het maximum aantal berichten op dat u kunt selecteren voor één inzending. Geldige waarden zijn 1 tot 50. De standaardwaarde is 15.

   - `BccEmailAddress` geeft extra BCC-geadresseerden op die een kopie van alle gebruikersinzendingen ontvangen. De standaardwaarde is leeg (geen extra BCC-geadresseerden).

   In dit voorbeeld wordt de 64-bits versie van de invoegversie geïnstalleerd vanaf het opgegeven pad met de standaardinstellingen.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   In dit voorbeeld wordt de 32-bits versie van de invoegversie geïnstalleerd vanaf het opgegeven pad met de volgende aanvullende instellingen:

   - Er kunnen maximaal 20 berichten worden geselecteerd in één inzending.
   - junkreports@contoso.com en hollyd@treyresearch.net BCC-kopieën van alle inzendingen ontvangen.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga als volgt te werk om te controleren of u de invoegvoegversie voor ongewenste e-mailrapportage hebt geïnstalleerd:

- Selecteer het bericht of open het bericht. Klik op **het tabblad** Start **of** Bericht op het lint op **Ongewenste e-mail** en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Rapporteren als Phishing**
  - **Opties voor het rapporteren van ongewenste e-mail**
  - **Help bij ongewenste e-mail melden**

  ![Ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint](../../media/junk-email-reporting-ribbon.png)

- Klik met de rechtermuisknop op het bericht, selecteer **Ongewenste e-mail** en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Rapporteren als Phishing**
  - **Opties voor het rapporteren van ongewenste e-mail**
  - **Help bij ongewenste e-mail melden**

  ![Meld ongewenste e-mail of phishing-e-mail met de rechtermuisknop](../../media/junk-email-reporting-right-click.png)

- Selecteer meerdere berichten, klik met de rechtermuisknop en controleer of de volgende opties beschikbaar zijn:

  - **Rapporteren als ongewenste e-mail**
  - **Rapporteren als Phishing**

  ![Meerdere ongewenste e-mailberichten of phishing-e-mailberichten rapporteren met de rechtermuisknop](../../media/junk-email-reporting-right-click-multiple.png)

- Doe de vorige acties in de map  **Ongewenste e-mail** en controleer of de vorige opties voor het rapporteren van ongewenste e-mail nu **Geen ongewenste e-mail zijn.**

  ![Geen ongewenste e-mail of phishing-e-mail rapporteren vanaf het lint in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapport geen ongewenste e-mail of phishing-e-mail van klik met de rechtermuisknop in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Meerdere niet-ongewenste e-mailberichten of phishingberichten rapporteren door met de rechtermuisknop te klikken in de map Ongewenste e-mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>De invoegvoegmap Voor het rapporteren van ongewenste e-mail verwijderen

Nadat u Outlook hebt gesloten, gebruikt u een van de volgende procedures om de invoegversie voor rapportage van ongewenste e-mail te verwijderen:

- **Configuratiescherm:** Druk op de Windows-toets + R. Typ in **het dialoogvenster** Uitvoeren dat wordt geopend en klik vervolgens `control appwiz.cpl` op **OK.**

  Zoek en selecteer **Microsoft Junk Email Reporting Add-in in** de lijst en klik vervolgens op **Verwijderen.**

- **Windows Installer-pakket:** zoek of download het juiste MSI-bestand en dubbelklik erop.

  - **32-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  Selecteer in het dialoogvenster dat wordt weergegeven de optie **Microsoft Junk Email Reporting Add-in** for Outlook verwijderen en klik vervolgens op **Volgende.**

- **Stille modus:** zoek of download het juiste MSI-bestand. Vervang in een opdrachtpromptvenster door de locatie van het \<PathToFile\> MSI-bestand en voer een van de volgende opdrachten uit:

  - **32-bits:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-bits:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Wanneer u Outlook opent na het verwijderen, moeten de opties voor ongewenste e-mail, geen ongewenste e-mail en phishingrapportage zijn verdwenen.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Problemen met de invoegmap Voor het rapporteren van ongewenste e-mail oplossen

Af en toe kan er problemen zijn met Outlook na het toevoegen van de invoegversie voor rapportage van ongewenste e-mail. In deze sectie worden problemen beschreven die u mogelijk ondervindt, samen met tips voor het oplossen van deze problemen.

### <a name="troubleshooting-for-users"></a>Probleemoplossing voor gebruikers

U ervaart een of meer van de volgende problemen:

- Er gebeurt niets wanneer u op **Ongewenste e-mail rapporteren klikt**
- Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd
- Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een antwoord dat niet kan worden bezorgd

Ga als volgt te werk om dit probleem op te lossen:

1. Sluit Outlook en start deze opnieuw.
2. Maak en verzend een testbericht en controleer of de geadresseerde het bericht heeft ontvangen.
3. Als het probleem zich blijft voordoen, neem dan contact op met de beheerder.

Zie Berichten en bestanden rapporteren bij Microsoft voor andere methoden die u kunt gebruiken om berichten bij Microsoft [in te dienen.](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>Probleemoplossing voor beheerders

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Probleem: er wordt voortdurend een foutbericht weergegeven waarin gebruikers worden gevraagd contact op te nemen met de systeembeheerder

1. Controleer of stel de `LoggingLevel` registersleutel in op de waarde 'Verbose':

   - **32-bits Outlook in 32-bits Windows:**

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

2. Start Outlook opnieuw en vraag gebruikers om terug te rapporteren wanneer ze het foutbericht zien.

3. Verzamel de logboekgegevens die op de volgende locatie zijn gevonden:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Neem contact op met de technische ondersteuning van Exchange Online Protection en geef ze de logboekgegevens.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Probleem: Gebruikers hebben geselecteerd om geen bevestigingsprompt te ontvangen wanneer ze berichten rapporteren, en nu willen ze de prompt terug

1. Maak de `ConfirmReportJunk` registersleutel met de waarde 'Waar':

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Start Outlook opnieuw.