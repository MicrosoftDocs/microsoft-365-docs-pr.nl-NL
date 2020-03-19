---
title: De invoeginvoeginstallatie voor ongewenste e-mailrapportage voor Microsoft Outlook installeren
f1.keywords:
- NOCSH
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: In dit artikelOndersteunde talenInstalleer de Invoegin voor ongewenste e-mailrapportage verwijderen Verwijder de invoegin voor ongewenste e-mailrapportageVoor meer informatie
ms.openlocfilehash: 0f7a5a3cbaddf9aef5e518db38ffb36c397cd1f0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805893"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>De invoeginvoeginstallatie voor ongewenste e-mailrapportage voor Microsoft Outlook installeren

In dit onderwerp wordt beschreven hoe u de invoegtoepassing Microsoft Ongewenste e-mailrapportage voor Outlook on client computers in uw organisatie installeren (en verwijderen). De huidige versie van de invoegtoepassing (januari 2016) bevat ondersteuning voor Outlook 2016, Outlook 2013 en Outlook 2010.

Met de invoegtoepassing (voor alle ondersteunde talen) u ongewenste e-mail rechtstreeks vanuit het Outlook-lint rapporteren. De Engelse versie van de invoegtoepassing bevat extra opties voor het melden van e-mailproblemen aan Microsoft, rechtstreeks vanaf het lint:

- Meld phishing scam e-mails die u ontvangt

- E-mail melden die onjuist is geïdentificeerd als ongewenste e-mail.

## <a name="supported-languages"></a>Ondersteunde talen
<a name="sectionSection0"> </a>

De invoegin aanvulling op ongewenste e-mailrapportage ondersteunt de volgende talen:

- Vereenvoudigd Chinees

- Traditioneel Chinees

- Nederlands

- Engels

- Frans

- Duits

- Italiaans

- Japans

- Koreaans

- Portugees

- Portugees (Brazilië)

- Spaans

## <a name="install-the-junk-email-reporting-add-in"></a>De invoeginvoeging ongewenste e-mailrapportage installeren

U de invoegin voor ongewenste e-mailrapportage installeren:

- Door het Windows Installer-pakket uit te voeren zoals elk ander .msi-bestand. Wanneer u de invoegtoepassing installeert, wordt er een GUI-interface geopend en wordt u door de installatieschermen geleid. Zie [De invoegin van ongewenste e-mailrapportage installeren met de wizard Setup](#install-the-junk-email-reporting-add-in-using-the-setup-wizard)voor meer informatie.

OF

- Door het uitvoeren van een stille installatie die de installatie user interface onderdrukt. In plaats daarvan geeft u opdrachtregelopties op die een installatiescript uitvoeren. Wanneer u de invoeginrichting installeert, zijn er extra configuratieopties beschikbaar die niet beschikbaar zijn via de GUI-interface. Zie [De invoegin van ongewenste e-mailrapportage](#install-the-junk-email-reporting-add-in-using-silent-mode)installeren met de stille modus voor meer informatie.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie de **systeemvereisten** voor de invoegin van ongewenste e-mailrapportage op [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275).

> [!NOTE]
> U moet beheerdersrechten hebben op de computer waarop u de invoeging installeert.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>De invoeginvoegplicht voor ongewenste e-mailrapportage installeren met de wizard Setup

1. Sluit Outlook op uw computer.

2. Download in de sectie **Details** van [Microsoft Ongewenste e-mail rapportage-invoegtoepassing voor Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)het juiste .msi-bestand voor uw versie van Office.

3. Dubbelklik op het .msi-bestand.

4. Klik op de pagina **Invoegtoepassing Voor ongewenste e-mailrapportage** van Microsoft op **Volgende**.

5. Bekijk de licentieovereenkomst en klik op **Ik accepteer de voorwaarden in de licentieovereenkomst** als u akkoord gaat met de installatievoorwaarden (vereist om de installatie voort te zetten). Klik op **Volgende** om door te gaan.

6. Wanneer de wizard is voltooid, klikt u op **Voltooien**.

7. Outlook starten.

8. Zoek naar de knop **Ongewenste** e-mail op het lint van Outlook. U nu ongewenste e-mailberichten melden aan Microsoft door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste** rapport te klikken.

9. Kies de pijl-omlaag naast **Ongewenste e-mail** voor meer opties, zoals **Rapporteren als Phishing** als u e-mails over phishing-fraude wilt melden bij Microsoft. In uw map ongewenste e-mail u ook, **Niet-ongewenste e-mail** melden selecteren als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>De invoeginvoeginstallatie voor ongewenste e-mailrapportage installeren met de stille modus

1. Sluit Outlook op uw computer.

2. Open een opdrachtprompt.

3. Als u een rechte installatie van de invoegtoepassing wilt uitvoeren, zonder optionele parameters, geeft u het volgende op:

   - Computers met x86 Outlook:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`

   - Computers met x64 Outlook:`msiexec /qn /i JunkReportingAdd-in.x64-en.msi`

    U ook de optionele parameters MaxMessageSelection en BccEmailAddress opgeven:

   - Met MaxMessageSelection kunnen beheerders het maximumaantal berichten definiëren dat door gebruikers kan worden geselecteerd voor indiening in één klik. Het bereik is 1 tot 50 berichten en de standaardwaarde is 10 berichten.

     Voorbeeld: Als u het maximumaantal berichten wilt instellen dat door gebruikers kan worden geselecteerd voor indiening in één klik op 16, gebruikt u de volgende optie als onderdeel van de installatieopdracht:`MaxMessageSelection=16`

   - BccEmailAddress stelt beheerders in staat om een postvak in te stellen om een kopie van al hun gebruikersinzendingen te ontvangen door een BCC-e-mailadres in te stellen. Wanneer het postvak is ingesteld, wordt een kopie van alle ingediende e-mails naar het BCCEmailAddress verzonden. Anders is de standaardinstelling geen BCC-e-mailadres.

     Voorbeeld: Als u junkReports@contoso.com als BCC-e-mailadres voor alle inzendingen wilt gebruiken, gebruikt u de volgende opdracht:`BccEmailAddress="junkReports@contoso.com"`

     > [!NOTE]
     > U meerdere BCC-e-mailadressen instellen door ze in te voeren met een puntkommascheiding. Voorbeeld:`BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`

     Als u beide optionele parameters wilt toevoegen op basis van de vorige voorbeelden, voert u de volgende opdracht uit op een computer met x86 Outlook:

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. Nadat de installatie is voltooid, start u Outlook.

5. Zoek naar de knop **Ongewenste** e-mail op het lint van Outlook. U nu ongewenste e-mailberichten melden aan Microsoft door de ongewenste e-mailberichten in uw Postvak IN te selecteren en op de knop **Ongewenste** rapport te klikken.

6. Kies de pijl-omlaag naast **Ongewenste e-mail** voor meer opties, zoals **Rapporteren als Phishing** als u e-mails over phishing-fraude wilt melden bij Microsoft. In uw map ongewenste e-mail u ook, **Niet-ongewenste e-mail** melden selecteren als een e-mail onjuist is geïdentificeerd als ongewenste e-mail.

## <a name="uninstall-the-junk-email-reporting-add-in"></a>De invoeginvoeging voor ongewenste e-mailrapportage verwijderen

Gebruik een van de opties die hierin worden beschreven om de invoegtoepassing Ongewenste e-mailrapportage te verwijderen:

- Verwijder de invoeging met het Windows Configuratiescherm.

- Voer het Installatiepakket van Windows uit en selecteer de optie Verwijderen.

- Voer een stille installatie uit met de optie Verwijderen.

> [!NOTE]
> U moet beheerdersrechten hebben op de computer waarop u de invoeging uitde.

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>De invoeginvoeging ongewenste e-mailrapportage verwijderen uit het Configuratiescherm

1. Sluit Outlook op uw computer.

2. Selecteer in het menu Start op uw computer **het Configuratiescherm**.

3. Selecteer **Programma's en onderdelen**.

4. Selecteer **Microsoft Ongewenste e-mail rapportage-invoegtoepassing voor Microsoft Office Outlook**.

5. Selecteer **Verwijderen**selecteren .

6. Start Outlook opnieuw om te bevestigen dat de invoegtoepassing niet meer wordt weergegeven op het Outlook-lint.

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>De invoeginvoegin voor ongewenste e-mailrapportage verwijderen door het Windows Installer-pakket uit te voeren

1. Sluit Outlook op uw computer.

   > [!NOTE]
   > Als Outlook wordt uitgevoerd tijdens het verwijderen van het proces, moet deze opnieuw worden gestart om de invoegtoepassing volledig te verwijderen.

2. Voer het .msi-bestand dat u eerder hebt uitgevoerd opnieuw uit om de invoegtoepassing te installeren.

   (Download in de sectie **Details** van [Microsoft Ongewenste e-mail rapportage-invoegtoepassing voor Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)het juiste .msi-bestand voor uw versie van Office en dubbelklik op het .msi-bestand.)

3. Volg de aanwijzingen om de invoegtoepassing te verwijderen.

4. Start Outlook opnieuw om te bevestigen dat de invoegtoepassing niet meer wordt weergegeven op het Outlook-lint.

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>De invoeginvoegin voor ongewenste e-mailrapportage verwijderen in de stille modus

1. Sluit Outlook op uw computer.

   > [!NOTE]
   > Als Outlook wordt uitgevoerd tijdens het verwijderen van het proces, moet deze opnieuw worden gestart om de invoegtoepassing volledig te verwijderen.

2. Open een opdrachtprompt.

3. Geef de volgende parameter voor de opdrachtregel op:

   Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

   Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

4. Start Outlook opnieuw om te bevestigen dat de invoegtoepassing niet meer wordt weergegeven op het Outlook-lint.

## <a name="for-more-information"></a>Voor meer informatie

[Ongewenste e-mailberichten melden aan Microsoft](report-junk-email-messages-to-microsoft.md)

[Informatie over probleemoplossing en ondersteuning](troubleshooting-and-support-information.md)
