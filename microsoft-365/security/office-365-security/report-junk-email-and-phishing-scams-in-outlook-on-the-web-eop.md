---
title: E-mail met ongewenste e-mail en phishing melden in de webversie van Outlook
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer te weten komen over de opties voor de ingebouwde e-mail, niet ongewenste e-mailrapportage in Outlook op het web (Outlook Web App) in Exchange Online en hoe u deze rapportageopties voor gebruikers uitschakelen.
ms.openlocfilehash: adbb4f16201e221bce2405a7b715dd6a630e9e1d
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617318"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>E-mail met ongewenste e-mail en phishing melden in de webversie van Outlook in Exchange Online

In Microsoft 365-organisaties met postvakken in Exchange Online u de ingebouwde rapportageopties in het web van Outlook (voorheen Outlook Web App) gebruiken om valse positieven (goede e-mail gemarkeerd als spam), false negatives (slechte e-mail toegestaan) en phishingberichten in te dienen bij Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Security & Compliance Center. Zie [Beheerdersinzending gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

- Beheerders kunnen de mogelijkheid voor gebruikers uitschakelen of inschakelen om berichten te rapporteren aan Microsoft in de webversie van Outlook. Zie de [sectie Ongewenste e-mail bijwerken of inschakelen in de websectie van Outlook](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) later in dit onderwerp voor meer informatie.

- U gerapporteerde berichten configureren die moeten worden gekopieerd of doorgestuurd naar een postvak dat u opgeeft. Zie [Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten in Exchange Online](user-submission.md)voor meer informatie.

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Spam- en phishingberichten melden in de webversie van Outlook

1. Voor berichten in het Postvak IN of een andere e-mailmap, behalve ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:

   - Selecteer het bericht, klik op **Ongewenste e-mail** op de werkbalk en selecteer **vervolgens Ongewenste e-mail** of **phishing**.

     ![E-mail met ongewenste e-mail of phishing melden vanaf het lint](../../media/owa-report-junk.png)

   - Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als ongewenste e-mail**.

2. Klik in het dialoogvenster dat wordt weergegeven op **Rapport**. Als u van gedachten verandert, klikt u op **Niet rapporteren**.

   ![Dialoogvenster Rapporteren als ongewenste e-mail](../../media/owa-report-as-junk-dialog.png)

   ![Dialoogvenster rapporteren als phishing](../../media/owa-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse. Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de verzonden berichten weer te geven.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Niet-spam- en phishingberichten rapporteren vanuit de map Ongewenste e-mail in de webversie van Outlook

1. Gebruik in de map Ongewenste e-mail een van de volgende methoden om spamalmerk-positieven of phishingberichten te melden:

   - Selecteer het bericht, klik op **Niet ongewenste e-mail** op de werkbalk en selecteer **Vervolgens Geen ongewenste e-mail** of **phishing**.

     ![E-mail met ongewenste e-mail of phishing melden vanaf het lint](../../media/owa-report-not-junk.png)

   - Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als niet-ongewenste e-mail**.

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport**. Als u van gedachten verandert, klikt u op **Niet rapporteren**.

   ![Dialoogvenster Rapporteren als niet-ongewenste e-mail](../../media/owa-report-as-not-junk-dialog.png)

   ![Dialoogvenster rapporteren als phishing](../../media/owa-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse. Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de verzonden berichten weer te geven.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Rapportage over ongewenste e-mail uitschakelen of inschakelen in de webversie van Outlook

Standaard kunnen gebruikers spamalmerk-positieven, valse negatieven en phishingberichten melden bij Microsoft voor analyse in de webversie van Outlook. Beheerders kunnen outlook op het webpostvakbeleid configureren in Exchange Online PowerShell om te voorkomen dat gebruikers spamalmerk-positieven en valse negatieven spam melden aan Microsoft. U de mogelijkheid voor gebruikers om phishingberichten aan Microsoft te melden niet uitschakelen.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt specifiek de rollen **Ontvangende beleidsregels** of **e-mailontvangers** nodig in Exchange Online, die standaard zijn toegewezen aan de rolgroepen **Organisatiebeheer** en Het beheer **van ontvangers.** Zie [Rolgroepen wijzigen in Exchange Online voor](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)meer informatie over rolgroepen in Exchange Online.

- Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u aangepaste beleidsregels maken. Aangepaste beleidsregels worden toegepast op scoped-gebruikers vóór het standaardbeleid. Zie [Outlook voor het webpostvakbeleid in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)voor meer informatie over het beleid voor webpostvak in Outlook.

- Als u rapportage over ongewenste e-mail uitschakelt, wordt een bericht niet als ongewenste of niet-ongewenste e-mail in de webversie van Outlook weergegeven. Als u een bericht selecteert in de map Ongewenste e-mail en op **Niet ongewenste** \> **e-mail klikken,** wordt het bericht nog steeds teruggeboekt naar het Postvak IN. Als u een bericht in een andere e-mailmap selecteert en op **Ongewenste** \> **e-mail** klikt, wordt het bericht nog steeds verplaatst naar de map Ongewenste e-mail. Wat niet meer beschikbaar is, is de optie om het bericht aan Microsoft te rapporteren.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Exchange Online PowerShell gebruiken om rapportage over ongewenste e-mail uit te schakelen of in te schakelen in de webversie van Outlook

1. Voer de volgende opdracht uit om uw bestaande beleid voor webpostvaks van Outlook en de status van rapportage over ongewenste e-mail te zoeken:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Als u rapportage over ongewenste e-mail wilt uitschakelen of inschakelen in de webversie van Outlook, gebruikt u de volgende syntaxis:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In dit voorbeeld wordt melding van ongewenste e-mail in het standaardbeleid uitgeschakeld.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In dit voorbeeld u rapportage via ongewenste e-mail maken in het aangepaste beleid met de naam Contoso Managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) en [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of ongewenste e-mailrapportage in de webversie van Outlook is ingeschakeld of uitgeschakeld, voert u een van de volgende stappen uit:

- Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de eigenschap **ReportJunkEmailEnabled-waarde:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Open het postvak van een betrokken gebruiker in de webversie **Junk** van Outlook, selecteer een bericht in het Postvak IN, klik op \> **Ongewenste e-mail** en controleer de prompt om het bericht aan Microsoft te rapporteren, al dan niet wordt weergegeven.<sup>\*</sup>

- Open het postvak van een betrokken gebruiker in de webversie van **Junk** Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op \> **Ongewenste e-mail** en controleer de prompt om het bericht aan Microsoft te rapporteren, al dan niet wordt weergegeven.<sup>\*</sup>

<sup>\*</sup>Gebruikers kunnen de prompt verbergen om het bericht te melden terwijl ze het bericht nog steeds rapporteren. Ga als volgt te werk om deze instelling in de webversie van Outlook te controleren:

1. Klik **op Instellingen** in het ![ pictogram Webinstellingen Bekijk alle ](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **e-mail met ongewenste e-mail met ongewenste e-mail van Outlook in de webinstellingen Bekijk alle e-mail met ongewenste e-mail van Outlook**.
2. Controleer in de sectie **Rapportage** de waarde: **Vraag het mij voordat u een rapport verzendt.**

   ![Instellingen voor e-mailrapportage in Outlook op het web](../../media/owa-junk-email-reporting-options.png)
