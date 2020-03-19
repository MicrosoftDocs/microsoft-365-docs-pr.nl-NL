---
title: Informatie over probleemoplossing en ondersteuning
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
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: In dit onderwerp worden stappen voor probleemoplossing voor eindgebruikers en beheerders beschreven en wordt informatie gegeven over hoe u contact opnemen met technische ondersteuning voor hulp.
ms.openlocfilehash: efb71aab852b76b2b898419444bfea4144728514
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811663"
---
# <a name="troubleshooting-and-support-information"></a>Informatie over probleemoplossing en ondersteuning

In dit onderwerp worden stappen voor probleemoplossing voor eindgebruikers en beheerders beschreven en wordt informatie gegeven over hoe u contact opnemen met technische ondersteuning voor hulp.

## <a name="troubleshooting-for-users"></a>Probleemoplossing voor gebruikers

Af en toe u problemen ondervinden met Microsoft Outlook nadat u de invoegtoepassing voor ongewenste e-mailrapportage hebt toegevoegd. Hieronder volgen problemen die u tegenkomen, samen met tips voor het oplossen van deze problemen.

- Er gebeurt niets wanneer u op **Ongewenste e-mail** melden klikt

- Outlook reageert niet meer nadat u een e-mailbericht hebt geselecteerd

- Gerapporteerde ongewenste e-mail kan niet worden bezorgd vanwege een "onbestelbaar" antwoord

Ga als volgt te werk om dit probleem op te lossen:

1. Outlook sluiten en opnieuw starten.

2. Controleer of u een testbericht maken en verzenden. Hiervoor u een testbericht verzenden naar een ander e-mailaccount waarvoor u verantwoordelijk bent en vervolgens controleren of het e-mailbericht is ontvangen.

Als het probleem blijft bestaan, neemt u contact op met uw beheerder.

> [!TIP]
> U ook spamberichten rechtstreeks naar Microsoft verzenden met behulp van het [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) e-mailadres en fout-positieve berichten met behulp van het [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) e-mailadres. Zie [Spam, niet-spam en phishing-scamberichten verzenden voor analyse voor](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)meer informatie.

## <a name="troubleshooting-for-administrators"></a>Probleemoplossing voor beheerders

Als beheerder u problemen ondervinden met gebruikers die de invoegtoepassing Ongewenste e-mailrapportage voor Outlook gebruiken. Hieronder volgen enkele tips voor het oplossen van problemen die u zou kunnen tegenkomen.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Probleem: er verschijnt voortdurend een foutbericht waarin gebruikers worden gevraagd contact op te nemen met hun systeembeheerder

1. Stel de volgende registersleutelwaarde in op "Verbose":

   - **32-bits Outlook geïnstalleerd op een 32-bits besturingssysteem:**

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32-bits Outlook geïnstalleerd op een 64-bits besturingssysteem:**

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64-bits Outlook (altijd geïnstalleerd op een 64-bits besturingssysteem):**

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Start Outlook opnieuw op en vraag gebruikers om terug te rapporteren wanneer ze het foutbericht zien.

3. Verzamel de loggegevens op de volgende locatie:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Neem contact op met de technische ondersteuning van Exchange Online Protection en geef hen de loggegevens.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Probleem: gebruikers kiezen ervoor om geen bevestiging te ontvangen wanneer ze een e-mail als ongewenste e-mail indienen en nu willen ze de optie terug

1. Stel de volgende registersleutelwaarde in `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`op 'Waar': .

2. Outlook opnieuw starten.

## <a name="support-information"></a>Ondersteuningsinformatie

Als u hulp nodig hebt bij de installatie, configuratie of ontinstallatie van de invoegtoepassing, neemt u contact op met de technische ondersteuning via de koppeling nieuwe serviceaanvraag op de ondersteuningspagina in het Microsoft 365-beheercentrum. Zie [Help en ondersteuning voor EOP voor](help-and-support-for-eop.md)extra opties, zoals het indienen van een serviceaanvraag via de telefoon en self-support.

## <a name="for-more-information"></a>Voor meer informatie

[De invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)

[Ongewenste e-mailberichten melden aan Microsoft](report-junk-email-messages-to-microsoft.md)
