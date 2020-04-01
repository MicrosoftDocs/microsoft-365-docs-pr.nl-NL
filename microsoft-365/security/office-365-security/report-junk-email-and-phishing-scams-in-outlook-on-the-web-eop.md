---
title: 'Ongewenste e-mail en phishing-scams melden in de webversie van Outlook '
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
description: Office 365-gebruikers met Exchange Online-postvakken kunnen outlook op internet (Outlook Web App) gebruiken om spam-, niet-spam- en phishingberichten naar Microsoft te verzenden voor analyse.
ms.openlocfilehash: b58e3ae5be9bf2a473b655287ad9bb1cb8ef2c78
ms.sourcegitcommit: 4d4d27a49eb258dc560439ca4baf61ebb9c1eff3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2020
ms.locfileid: "43075618"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a>Ongewenste en phishing-e-mail melden in de webversie van Outlook in Office 365

Als u een Office 365-klant bent met Exchange Online-postvakken, u de ingebouwde rapportageopties in Outlook op de web (voorheen Outlook Web App) gebruiken om false positives (goede e-mail gemarkeerd als spam), valse negatieven (slechte e-mail toegestaan) en phishing-berichten in te dienen bij Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u een beheerder bent in een Office 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Office 365 Security & Compliance Center. Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

- Beheerders kunnen de mogelijkheid voor gebruikers om berichten aan Microsoft te melden in de webversie van Outlook uitschakelen of inschakelen. Zie de [rapportage over ongewenste e-mail in de websectie](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook later in dit onderwerp voor meer informatie.

- Zie [Berichten en bestanden rapporteren aan Microsoft in Office 365](report-junk-email-messages-to-microsoft.md)voor meer informatie over het rapporteren van berichten aan Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Spam- en phishingberichten melden in de webversie van Outlook

1. Voor berichten in het Postvak IN of een andere e-mailmap, met uitzondering van ongewenste e-mail, gebruikt u een van de volgende methoden om spam- en phishingberichten te melden:

   - Selecteer het bericht, klik op **Ongewenste e-mail** op de werkbalk en selecteer **Ongewenste** **of phishing.**

     ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/owa-report-junk.png)

   - Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als ongewenste e-mail.**

2. Klik in het dialoogvenster dat wordt weergegeven op **Rapport**. Als u van gedachten verandert, klikt u op **Niet rapporteren.**

   ![Rapport als pictogram ongewenste e-mail](../../media/owa-report-as-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/owa-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse. Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Niet-spam- en phishingberichten melden vanuit de map Ongewenste e-mail in de webversie van Outlook

1. Gebruik in de map Ongewenste e-mail een van de volgende methoden om valse positieven of phishingberichten te melden:

   - Selecteer het bericht, klik op **Geen ongewenstee informatie** op de werkbalk en selecteer **Geen ongewenste e-mail** of **phishing**.

     ![Ongewenste of phishing-e-mail melden vanaf het lint](../../media/owa-report-not-junk.png)

   - Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als geen ongewenste e-mail.**

2. Lees in het dialoogvenster dat wordt weergegeven de informatie en klik op **Rapport**. Als u van gedachten verandert, klikt u op **Niet rapporteren.**

   ![Rapport als niet-ongewenste dialoogvenster](../../media/owa-report-as-not-junk-dialog.png)

   ![Rapport als dialoogvenster phishing](../../media/owa-report-as-phishing-dialog.png)

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse. Als u wilt bevestigen dat de berichten zijn verzonden, opent u de map **Verzonden items** om de ingediende berichten weer te geven.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Meldingen van ongewenste e-mail uitschakelen of inschakelen in de webversie van Outlook

Standaard kunnen gebruikers spamfout-positieven, valse negatieven en phishingberichten melden aan Microsoft voor analyse in de webversie van Outlook. Beheerders kunnen Outlook configureren op het beleid voor webpostvakinen in Exchange Online PowerShell om te voorkomen dat gebruikers valse positieven en spamnegatieven melden bij Microsoft. U de mogelijkheid voor gebruikers om phishingberichten aan Microsoft te melden niet uitschakelen.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt met name de rollen **Geadresseerden** of **Geadresseerden** nodig in Exchange Online, die standaard zijn toegewezen aan de rolgroepen **Organisatiebeheer** en **Geadresseerdbeheer.** Zie [Rolgroepen wijzigen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)voor meer informatie over rolgroepen in Exchange Online .

- Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u aangepaste beleidsregels maken. Aangepaste beleidsregels worden toegepast op gebruikers met scopen vóór het standaardbeleid. Zie [Outlook voor het webpostvakbeleid in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)voor meer informatie over het beleid voor webpostvak.

- Als u ongewenste e-mailrapportage uitschakelt, wordt de mogelijkheid om een bericht te markeren niet als ongewenste e-mail verwijderd of niet als ongewenste e-mail in de webversie van Outlook. Als u een bericht selecteert in de map Ongewenste e-mail en op **Niet ongewenstee berichten** \> **klikt,** wordt het bericht nog steeds teruggezet naar het Postvak IN. Als u een bericht selecteert in een andere e-mailmap en op **Ongewenste e-mail** \> **klikt,** wordt het bericht nog steeds verplaatst naar de map Ongewenste e-mail. Wat niet meer beschikbaar is, is de optie om het bericht aan Microsoft te rapporteren.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Exchange Online PowerShell gebruiken om meldingen van ongewenste e-mail uit te schakelen of in te schakelen in de webversie van Outlook

1. Voer de volgende opdracht uit om uw bestaande Outlook voor het webpostvakbeleid en de status van ongewenste e-mailrapportage te vinden:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Als u de rapportage met ongewenste e-mail wilt uitschakelen of inschakelen in de webversie van Outlook, gebruikt u de volgende syntaxis:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In dit voorbeeld wordt melding van ongewenste e-mail in het standaardbeleid uitgeschakeld.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In dit voorbeeld wordt melding van ongewenste e-mail mogelijk gemaakt in het aangepaste beleid met de naam Contoso Managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) en [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Gebruik een van de volgende stappen om te controleren of u de rapportage over ongewenste e-mail in Outlook hebt ingeschakeld of uitgeschakeld in de webversie van Outlook:

- Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de eigenschapswaarde **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Open het postvak van een betrokken gebruiker in de webversie van Outlook, selecteer een bericht in het Postvak IN, klik op **Ongewenste** \> **e-mail** en controleer of de prompt om het bericht aan Microsoft te melden wel of niet wordt weergegeven.<sup>\*</sup>

- Open het postvak van een betrokken gebruiker in de webversie van Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op **Ongewenste** \> **e-mail** en controleer of het bericht aan Microsoft wordt gemeld of niet wordt weergegeven.<sup>\*</sup>

<sup>\*</sup>Gebruikers kunnen de prompt verbergen om het bericht te rapporteren terwijl ze het bericht nog steeds rapporteren. Ga als volgt te werk om deze instelling in de webversie van Outlook te controleren:

1. Klik op **Instellingen** ![Outlook](../../media/owa-settings-icon.png) \> op het pictogram Webinstellingen Bekijk alle **ongewenste e-mail van** **Outlook-instellingen** \> .
2. Controleer in de sectie **Rapportage** de waarde: **Vraag het mij voordat u een rapport verzendt.**

   ![Instellingen voor meldingen van ongewenste e-mail in Outlook op de web](../../media/owa-junk-email-reporting-options.png)
