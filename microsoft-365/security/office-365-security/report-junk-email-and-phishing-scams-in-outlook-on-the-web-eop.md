---
title: Ongewenste e-mail en phishing in Outlook op internet
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
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor het rapporteren van ongewenste e-mail, geen ongewenste e-mail en phishing in Outlook op het web (Outlook Web App) in Exchange Online en hoe u deze rapportageopties voor gebruikers uit kunt schakelen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788305"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Meld ongewenste e-mail en phishing-Outlook op internet in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of on-premises postvakken met hybride moderne [verificatie,](../../enterprise/hybrid-modern-auth-overview.md)kunt u fout-positieven (goede e-mail gemarkeerd als spam), onwaar negatieven (slechte e-mail toegestaan) en phishingberichten verzenden naar Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

> [!IMPORTANT]
> We raden u aan de invoeging Rapportbericht of de invoeging Phishing melden voor gebruikersinzendingen. Zie Het rapportbericht inschakelen of de phishing-invoegvoegingen rapporteren [voor meer informatie.](./enable-the-report-message-add-in.md) We raden u de ingebouwde rapportageervaring in Outlook omdat het beleid voor het indienen van gebruikers niet [kan worden gebruikt.](./user-submission.md)

- Als u een beheerder bent in een organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

- Beheerders kunnen de mogelijkheid uitschakelen of inschakelen voor gebruikers om berichten te rapporteren aan Microsoft in Outlook op internet. Zie de sectie Ongewenste e-mail uitschakelen of [inschakelen in](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) Outlook sectie op het web verder in dit artikel voor meer informatie.

- U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Rapportage over ongewenste e-mail uitschakelen of inschakelen in Outlook op internet

Gebruikers kunnen standaard spam-fout-positieven, onwaar negatieven en phishingberichten aan Microsoft rapporteren voor analyse in Outlook op internet. Beheerders kunnen Outlook beleidsregels voor webpostvakken configureren in Exchange Online PowerShell om te voorkomen dat gebruikers fout-positieve e-mail en ongewenste ongewenste e-mail rapporteren aan Microsoft. U kunt de mogelijkheid voor gebruikers om phishingberichten bij Microsoft te melden niet uitschakelen.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- Voordat u de procedures in dit artikel kunt uitvoeren, moet Exchange Online machtigingen zijn toegewezen. U hebt met name de rollen **Geadresseerdenbeleid** of  E-mailontvangers nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer en Geadresseerdenbeheer.   Zie Machtigingen [in](/exchange/permissions-exo/permissions-exo) Exchange Online en Rolgroepen Exchange Online wijzigen in Exchange Online voor meer informatie over [rollengroepen in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)

- Elke organisatie heeft een standaardbeleid met de naam OwaMailboxPolicy-Default, maar u kunt aangepaste beleidsregels maken. Aangepaste beleidsregels worden toegepast op gebruikers met een bereik vóór het standaardbeleid. Zie het beleid voor Outlook webpostvak in Exchange Online voor meer informatie over Outlook beleidsregels [voor webpostvakken.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Als u rapportage over ongewenste e-mail uitwijst, wordt de mogelijkheid om een bericht te markeren als ongewenste e-mail niet verwijderd in Outlook op internet. Als u een bericht selecteert in de map Ongewenste e-mail en op Geen **ongewenste** e-mail klikt, wordt het bericht nog steeds \>  verplaatst naar het Postvak IN. Als u een bericht selecteert in een andere e-mailmap en op **Ongewenste e-mail** klikt, wordt het bericht nog steeds \>  verplaatst naar de map Ongewenste e-mail. Wat niet meer beschikbaar is, is de optie om het bericht aan Microsoft te rapporteren.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Gebruik Exchange Online PowerShell om rapportage van ongewenste e-mail uit te schakelen of in te schakelen in Outlook op internet

1. Voer de volgende opdracht uit Outlook voor het zoeken naar uw bestaande Outlook beleidsregels voor het webpostvak en de status van rapportage van ongewenste e-mail:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Gebruik de volgende syntaxis om het rapporteren van ongewenste e-mail in Outlook op internet uit te schakelen of in te schakelen:

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

Als u wilt controleren of u het rapporteren van ongewenste e-mail hebt ingeschakeld of uitgeschakeld in Outlook op internet, gebruikt u een van de volgende stappen:

- Voer Exchange Online PowerShell de volgende opdracht uit en controleer de **eigenschapswaarde ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Open het postvak van een betrokken gebruiker in Outlook op internet, selecteer  een bericht in het Postvak IN, klik op Ongewenste e-mail en controleer of de prompt om het bericht aan Microsoft te melden wel of niet wordt \>  weergegeven.<sup>\*</sup>

- Open het postvak van een betrokken gebruiker in Outlook op internet, selecteer  een bericht in de map Ongewenste e-mail, klik op Ongewenste e-mail en controleer of de prompt om het bericht aan Microsoft te melden wel of niet wordt \>  weergegeven.<sup>\*</sup>

<sup>\*</sup> Gebruikers kunnen de prompt voor het rapporteren van het bericht verbergen terwijl ze het bericht nog steeds rapporteren. U kunt deze instelling controleren in Outlook op internet:

1. Klik **Instellingen** ![ Outlook op het pictogram Webinstellingen Alle Outlook instellingen Ongewenste ](../../media/owa-settings-icon.png) \> **e-mail** \> **weergeven.**
2. Controleer in **de sectie** Rapportage de waarde: Vraag het mij voordat u een **rapport verstuurt.**

   ![Outlook instellingen voor het rapporteren van ongewenste e-mail op het web](../../media/owa-junk-email-reporting-options.png)
