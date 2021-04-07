---
title: Ongewenste e-mail en phishing-e-mail rapporteren in de webversie van Outlook
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
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor het rapporteren van ongewenste e-mail, geen ongewenste e-mail en phishing in de webversie van Outlook (Outlook Web App) in Exchange Online, en over het uitschakelen van deze rapportageopties voor gebruikers.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615208"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Ongewenste e-mail en phishing-e-mail rapporteren in de webversie van Outlook in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of on-premises postvakken die gebruikmaken van hybride moderne [verificatie,](../../enterprise/hybrid-modern-auth-overview.md)kunt u false positives (goede e-mail gemarkeerd als spam), onwaar negatieven (slechte e-mail toegestaan) en phishingberichten indienen bij Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Voor de beste gebruikersinzendingservaring raden we u aan het rapportbericht en de phishing-invoegvoegingen rapporteren te gebruiken. Zie [De invoeging Rapportbericht inschakelen](./enable-the-report-message-add-in.md) en De invoeging [Bij phishing melden inschakelen](./enable-the-report-phish-add-in.md) voor meer informatie.

- Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

- Beheerders kunnen de mogelijkheid uitschakelen of inschakelen voor gebruikers om berichten te rapporteren aan Microsoft in de webversie van Outlook. Zie de sectie Rapportering van ongewenste [e-mail uitschakelen of inschakelen in de webversie](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook verder in dit artikel voor meer informatie.

- U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Rapportage over ongewenste e-mail uitschakelen of inschakelen in de webversie van Outlook

Gebruikers kunnen standaard fout-positieven, onwaar negatieven en phishingberichten rapporteren aan Microsoft voor analyse in de webversie van Outlook. Beheerders kunnen beleidsregels voor outlook op het webpostvak configureren in Exchange Online PowerShell om te voorkomen dat gebruikers fout-positieve e-mail en ongewenste ongewenste e-mail rapporteren aan Microsoft. U kunt de mogelijkheid voor gebruikers om phishingberichten bij Microsoft te melden niet uitschakelen.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen krijgen toegewezen in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rollen **Geadresseerdenbeleid** of  E-mailontvangers nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer en Geadresseerdenbeheer.   Zie Machtigingen [in Exchange Online](/exchange/permissions-exo/permissions-exo) en Rollengroepen wijzigen in Exchange Online voor meer informatie over [rollengroepen in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)

- Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u kunt aangepaste beleidsregels maken. Aangepaste beleidsregels worden toegepast op gebruikers met een bereik vóór het standaardbeleid. Zie Beleidsregels voor postvakken in Outlook op het web in Exchange Online voor meer informatie over beleidsregels voor postvakken [in de webversie van Outlook.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Als u rapportage over ongewenste e-mail uitwijst, wordt de mogelijkheid om een bericht te markeren als ongewenste e-mail niet verwijderd in de webversie van Outlook. Als u een bericht selecteert in de map Ongewenste e-mail en op Geen **ongewenste** e-mail klikt, wordt het bericht nog steeds \>  verplaatst naar het Postvak IN. Als u een bericht selecteert in een andere e-mailmap en op **Ongewenste e-mail** klikt, wordt het bericht nog steeds \>  verplaatst naar de map Ongewenste e-mail. Wat niet meer beschikbaar is, is de optie om het bericht aan Microsoft te rapporteren.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Exchange Online PowerShell gebruiken om rapportage van ongewenste e-mail uit te schakelen of in te schakelen in de webversie van Outlook

1. Voer de volgende opdracht uit om uw bestaande beleidsregels voor outlook op het webpostvak en de status van rapportage van ongewenste e-mail te vinden:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Als u rapportage over ongewenste e-mail wilt uitschakelen of inschakelen in de webversie van Outlook, gebruikt u de volgende syntaxis:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In dit voorbeeld wordt rapportage van ongewenste e-mail uitgeschakeld in het standaardbeleid.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In dit voorbeeld kunt u melding maken van ongewenste e-mail in het aangepaste beleid met de naam Contoso-managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Zie Get-OwaMailboxPolicy and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy) [(Get-OwaMailboxPolicy)](/powershell/module/exchange/get-owamailboxpolicy) voor gedetailleerde syntaxis- en parametergegevens.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u het rapporteren van ongewenste e-mail hebt ingeschakeld of uitgeschakeld in de webversie van Outlook, gebruikt u een van de volgende stappen:

- Voer in Exchange Online PowerShell de volgende opdracht uit en controleer de **eigenschapswaarde ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Open het postvak van een getroffen gebruiker in de webversie  van Outlook, selecteer een bericht in het Postvak IN, klik op Ongewenste e-mail en controleer of de prompt om het bericht aan Microsoft te rapporteren al dan niet \>  wordt weergegeven.<sup>\*</sup>

- Open het postvak van een getroffen gebruiker in de webversie van  Outlook, selecteer een bericht in de map Ongewenste e-mail, klik op Ongewenste e-mail en controleer of de prompt om het bericht aan Microsoft te rapporteren al dan niet \>  wordt weergegeven.<sup>\*</sup>

<sup>\*</sup> Gebruikers kunnen de prompt voor het rapporteren van het bericht verbergen terwijl ze het bericht nog steeds rapporteren. Als u deze instelling wilt controleren in de webversie van Outlook:

1. Klik **op Instellingen** pictogram Outlook op de ![ webinstellingen Alle ](../../media/owa-settings-icon.png) \> **Outlook-instellingen** \> **Ongewenste e-mail weergeven.**
2. Controleer in **de sectie** Rapportage de waarde: Vraag het mij voordat u een **rapport verstuurt.**

   ![Instellingen voor rapportering van ongewenste e-mail in Outlook op het web](../../media/owa-junk-email-reporting-options.png)