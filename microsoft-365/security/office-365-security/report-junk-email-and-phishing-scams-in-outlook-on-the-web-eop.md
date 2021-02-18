---
title: Ongewenste e-mail en phishing-e-mail melden in de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor ongewenste e-mail, geen ongewenste e-mail en phishing-e-mailrapportage in de webversie van Outlook (Outlook Web App) in Exchange Online, en informatie over het uitschakelen van deze rapportageopties voor gebruikers.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0bd2da9b774b3557ebb820102ba86c17ebe44c69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289219"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Ongewenste e-mail en phishing-e-mail melden in de webversie van Outlook in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online kunt u de ingebouwde rapportageopties in de webversie van Outlook (voorheen Outlook Web App) gebruiken om fout-positieven (goede e-mail gemarkeerd als spam), fout-negatieven (niet-toegestane e-mail) en phishingberichten in te dienen bij Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum. Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.

- Beheerders kunnen de mogelijkheid voor gebruikers om berichten te rapporteren in De webversie van Outlook, uitschakelen of inschakelen. Zie voor meer informatie het gedeelte over het uitschakelen of inschakelen van rapportage van ongewenste e-mail in de [webversie](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook verder naar dit artikel.

- U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)

- Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over het rapporteren van berichten [naar Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Spam en phishingberichten rapporteren in de webversie van Outlook

1. Voor berichten in het Postvak IN of een andere e-mailmap behalve Ongewenste e-mail gebruikt u een van de volgende methoden om spam en phishingberichten te melden:

   - Selecteer het bericht, klik op **Ongewenste e-mail** op de werkbalk en selecteer vervolgens **Ongewenste e-mail** of **Phishing.**

     ![Ongewenste e-mail of phishing-e-mail melden via het lint](../../media/owa-report-junk.png)

   - Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer **Markeren als ongewenste e-mail.**

2. Klik in het dialoogvenster dat wordt weergegeven op **Rapport.** Als u van gedachten verandert, klikt u **op Niet rapporteren.**

   |Ongewenste e-mail|Phishing|
   |:---:|:---:|
   |![Dialoogvenster Rapporteren als ongewenste e-mail](../../media/owa-report-as-junk-dialog.png)|![Dialoogvenster Als phishing melden](../../media/owa-report-as-phishing-dialog.png)|

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse. Als u wilt controleren of de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Niet-spam en phishingberichten melden vanuit de map Ongewenste e-mail in de webversie van Outlook

1. Gebruik in de map Ongewenste e-mail een van de volgende methoden om fout-positieven of phishingberichten te melden:

   - Selecteer het bericht, klik op **Geen ongewenste** e-mail op de werkbalk en selecteer vervolgens **Geen ongewenste e-mail** of **Phishing.**

     ![Geen ongewenste e-mail of geen phishing-e-mail vanaf het lint melden](../../media/owa-report-not-junk.png)

   - Selecteer een of meer berichten, klik met de rechtermuisknop en selecteer Markeren **als niet-ongewenste e-mail.**

2. Lees de informatie in het dialoogvenster dat wordt weergegeven en klik op **Rapport.** Als u van gedachten verandert, klikt u **op Niet rapporteren.**

   |Geen ongewenste e-mail|Phishing|
   |:---:|:---:|
   |![Dialoogvenster Rapporteren als niet-ongewenste e-mail](../../media/owa-report-as-not-junk-dialog.png)|![Dialoogvenster Als phishing melden](../../media/owa-report-as-phishing-dialog.png)|

3. De geselecteerde berichten worden naar Microsoft verzonden voor analyse. Als u wilt controleren of de berichten zijn verzonden, opent u de map Verzonden **items** om de verzonden berichten te bekijken.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Rapportage van ongewenste e-mail in- of uitschakelen in de webversie van Outlook

Standaard kunnen gebruikers fout-positieven, fout-negatieven en phishingberichten rapporteren aan Microsoft voor analyse in de webversie van Outlook. Beheerders kunnen postvakbeleidsregels voor de webversie van Outlook configureren in Exchange Online PowerShell om te voorkomen dat gebruikers fout-positieven en fout-negatieven voor spam melden aan Microsoft. U kunt de mogelijkheid voor gebruikers om phishing-berichten te melden bij Microsoft niet uitschakelen.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen toegewezen krijgen in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rollen **Geadresseerdenbeleid** of  **E-mailontvangers** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer en **Geadresseerdenbeheer.** Zie Machtigingen in [Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) en Rollengroepen wijzigen in Exchange Online voor meer informatie over [rollengroepen in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)

- Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u kunt aangepaste beleidsregels maken. Aangepaste beleidsregels worden vóór het standaardbeleid toegepast op gebruikers met een bereik. Zie postvakbeleidsregels in de webversie van Outlook in Exchange Online voor meer informatie over postvakbeleidsregels [in de webversie van Outlook.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Het uitschakelen van rapportage van ongewenste e-mail betekent niet dat u een bericht in de webversie van Outlook kunt markeren als ongewenste e-mail of als ongewenste e-mail. Als u een bericht selecteert  in de map Ongewenste e-mail en op Geen ongewenste e-mail klikt, wordt het bericht weer verplaatst \>  naar het Postvak IN. Als u een bericht selecteert  in een andere e-mailmap en op Ongewenste e-mail klikt, wordt het bericht nog steeds verplaatst \>  naar de map Ongewenste e-mail. Wat niet meer beschikbaar is, is de optie om het bericht te rapporteren bij Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Exchange Online PowerShell gebruiken om rapportage van ongewenste e-mail in of uit te schakelen in de webversie van Outlook

1. Voer de volgende opdracht uit om uw bestaande postvakbeleidsregels voor de webversie van Outlook en de status van het rapporteren van ongewenste e-mail te vinden:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Gebruik de volgende syntaxis om rapportage van ongewenste e-mail in of uit te schakelen in de webversie van Outlook:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In dit voorbeeld wordt rapportage van ongewenste e-mail in het standaardbeleid uitgeschakeld.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In dit voorbeeld wordt rapportage van ongewenste e-mail in het aangepaste beleid met de naam Contoso-beheerders mogelijk gemaakt.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) en [Set-OwaMailboxPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)gedetailleerde syntaxis- en parameterinformatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u rapportage van ongewenste e-mail hebt ingeschakeld of uitgeschakeld in de webversie van Outlook, gebruikt u een van de volgende stappen:

- Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de waarde van de eigenschap **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Open het postvak van een getroffen gebruiker in de webversie  van Outlook, selecteer een bericht in het Postvak IN, klik op Ongewenste e-mail en controleer of de prompt voor het rapporteren van het bericht aan Microsoft wel of niet \>  wordt weergegeven.<sup>\*</sup>

- Open het postvak van een getroffen gebruiker in de webversie van  Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op Ongewenste e-mail en controleer of de prompt voor het rapporteren van het bericht aan Microsoft wel of niet wordt \>  weergegeven.<sup>\*</sup>

<sup>\*</sup> Gebruikers kunnen de prompt voor het rapporteren van het bericht verbergen terwijl ze het bericht nog steeds rapporteren. Deze instelling controleren in de webversie van Outlook:

1. Klik **op het** pictogram Instellingen voor de ![ webinstellingen van Outlook Alle ](../../media/owa-settings-icon.png) \> **Outlook-instellingen voor** ongewenste \> **e-mail weergeven.**
2. Controleer in **de sectie** Rapportage de waarde: Mij vragen voordat u een **rapport verstuurt.**

   ![Instellingen voor rapportage van ongewenste e-mail in Outlook op het web](../../media/owa-junk-email-reporting-options.png)
