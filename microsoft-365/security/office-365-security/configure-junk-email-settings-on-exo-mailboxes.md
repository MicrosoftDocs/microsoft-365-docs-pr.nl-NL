---
title: Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u de instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken. Veel van deze instellingen zijn beschikbaar voor gebruikers in de webversie van Outlook of Outlook.
ms.openlocfilehash: 689cec3f6a8b12764d03c98d23a9eb7ab6ca8e5e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638438"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes-in-office-365"></a>Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Office 365

Organisatorische antispaminstellingen in Exchange Online worden beheerd door Exchange Online Protection (EOP). Zie [Antispambeleid in Office 365](anti-spam-protection.md) voor meer informatie.

Maar er zijn ook specifieke antispam-instellingen die beheerders kunnen configureren op afzonderlijke postvakken in Exchange Online:

- **Regel ongewenste e-mail in- of uitschakelen**: de regel voor ongewenste e-mail is een verborgen regel voor Postvak In met de naam Ongewenste e-mailregel die standaard in elk postvak is ingeschakeld. De regel ongewenste e-mail bepaalt de volgende functies:

  - **Berichten verplaatsen naar de map Ongewenste e-mail op basis van antispambeleid:** wanneer een antispambeleid is geconfigureerd met de actie **Bericht verplaatsen naar ongewenste e-mail** voor een spamfiltervonnis, wordt het bericht met de filterregel voor ongewenste e-mail verplaatst naar de map Ongewenste e-mail nadat het bericht in het postvak is bezorgd. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie over spamfilteringsvonnissen in antispambeleid. Als automatisch verwijderen (ZAP) spam of phish detecteert in een bericht dat al is bezorgd, wordt het bericht met de filterregel voor ongewenste e-mail verplaatst naar de map Ongewenste e-mail voor Spam-spam die spam filtert naar ongewenste **e-mail.** Zie [Zero-hour auto purge (ZAP) - bescherming tegen spam en malware in Office 365](zero-hour-auto-purge.md)voor meer informatie over ZAP.
  
  - **Instellingen voor ongewenste e-mail die gebruikers zelf configureren in Outlook of Outlook op het web:** de _safelist-verzameling_ is de lijst Veilige afzenders, de lijst Veilige geadresseerden en de lijst Afzenders blokkeren in elk postvak. De vermeldingen in deze lijsten bepalen of de regel voor ongewenste e-mail het bericht verplaatst naar het Postvak IN of de map Ongewenste e-mail. Gebruikers kunnen de safelist-verzameling configureren voor hun eigen postvak in Outlook of de webversie van Outlook (voorheen Outlook Web App genoemd). Beheerders kunnen de safelist-verzameling configureren in het postvak van elke gebruiker.

Wanneer de regel voor ongewenste e-mail is ingeschakeld in het postvak, kan EOP berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie voor het filteren van spam **Verplaatsen Naar de map Ongewenste e-mail** of de lijst Geblokkeerde afzenders in het postvak en voorkomen dat berichten worden bezorgd in de map Ongewenste e-mail (op basis van de lijst Veilige afzenders in het postvak).

 Wanneer de regel voor ongewenste e-mail is uitgeschakeld in het postvak, kan EOP geen berichten verplaatsen naar de map Ongewenste e-mail op basis van de spamfilteractie **Bericht verplaatsen naar de map Ongewenste e-mail** of de safelist-verzameling in het postvak.

Beheerders kunnen Exchange Online PowerShell gebruiken om de status van de regel voor ongewenste e-mail op postvakken uit te schakelen, in te schakelen en weer te geven. Beheerders kunnen Exchange Online PowerShell ook gebruiken om vermeldingen in de safelist-verzameling op postvakken te configureren (de lijst Veilige afzenders, de lijst Met veilige geadresseerden en de lijst Afzenders blokkeren).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U Exchange Online PowerShell alleen gebruiken om deze procedures uit te voeren. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen krijgen voordat u deze procedures uitvoeren. U hebt in het bijzonder de rol **E-mailgeadresseerden** nodig (die standaard is toegewezen aan de rolgroepen **Organisatiebeheer,** **Geadresseerden**en **Aangepaste geadresseerden)** of de rol **Gebruikersopties** (die standaard is toegewezen aan de rolgroepen **Organisatiebeheer** en **helpdesk).** Zie [Rolgroepen wijzigen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)als u gebruikers wilt toevoegen aan rolgroepen in Exchange Online. Houd er rekening mee dat een gebruiker met standaardmachtigingen dezelfde procedures kan uitvoeren in zijn eigen postvak, zolang hij toegang heeft [tot Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)

- In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell gebruiken om de regel voor ongewenste e-mail in een postvak in te schakelen of uit te schakelen

> [!NOTE]
> U de cmdlet **Set-MailboxJunkEmailConfiguration** alleen gebruiken om de regel voor ongewenste e-mail uit te schakelen in een postvak dat is geopend in Outlook (in de exchange-modus in cache) of de webversie van Outlook. Als het postvak niet is geopend, ontvangt u `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` de fout: Als u deze fout `-ErrorAction SlientlyContinue` wilt onderdrukken voor bulkbewerkingen, u de opdracht **Set-MailboxJunkEmailConfiguration** toevoegen

Als u de regel voor ongewenste e-mail in een postvak wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In dit voorbeeld wordt de regel voor ongewenste e-mail op de mailbox van Ori Epstein uitgeschakeld.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In dit voorbeeld wordt de regel voor ongewenste e-mail uitgeschakeld voor alle gebruikerspostvakken in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Zie [Set-MailboxJunkEmailConfiguration voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)gedetailleerde syntaxis- en parametergegevens.

 **Opmerkingen**:

- Als de gebruiker zijn postvak nooit heeft geopend, ontvangt u mogelijk een foutmelding wanneer u de vorige opdracht uitvoert. Als u deze fout voor `-ErrorAction SlientlyContinue` bulkbewerkingen wilt onderdrukken, voegt u toe aan de opdracht **Set-MailboxJunkEmailConfiguration.**

- Zelfs als u de regel voor ongewenste e-mail uitschakelt, kan het filter voor ongewenste e-mail (afhankelijk van hoe het is geconfigureerd) ook bepalen of een bericht spam is en berichten verplaatsen naar de map Postvak IN of Ongewenste e-mail op basis van het eigen spamvonnis en de safelist-verzameling in het postvak. Zie de instellingen [voor ongewenste e-mail in de](#about-junk-email-settings-in-outlook) sectie Outlook in dit onderwerp voor meer informatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de regel voor ongewenste e-mail in een postvak hebt ingeschakeld of uitgeschakeld, gebruikt u een van de volgende procedures:

- Vervang _ \<\> PostvakIdentiteit_ door de naam, alias of e-mailadres van het postvak en voer de volgende opdracht uit om de waarde van de **eigenschap Ingeschakeld** te verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

- Vervang _ \<PostvakIdentiteit\> _ door de naam, alias of e-mailadres van het postvak en voer de volgende opdracht uit om de **eigenschapswaarde Ingeschakeld** van de regel voor ongewenste e-mail te verifiëren.

  ```PowerShell
  Get-InboxRule "Junk E-mail Rule" -Mailbox "<MailboxIdentity>" -IncludeHidden
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell gebruiken om de safelist-verzameling in een postvak te configureren

De safelist-verzameling in een postvak bevat de lijst Veilige afzenders, de lijst Veilige geadresseerden en de lijst Geblokkeerde afzenders. Standaard kunnen gebruikers de safelist-verzameling configureren in hun eigen postvak in Outlook of de webversie van Outlook. Beheerders kunnen de bijbehorende parameters op de cmdlet **Set-MailboxJunkEmailConfiguration** gebruiken om de safelist-verzameling op het postvak van een gebruiker te configureren. Deze parameters worden beschreven in de volgende tabel.

|||
|---|---|
|**Parameter op Set-MailboxJunkEmailConfiguration**|**Outlook voor de webinstelling**|
|_Geblokkeerde afzendersendomeinen_|**E-mail van deze afzenders of domeinen verplaatsen naar mijn map Ongewenste e-mail**|
|_Contactpersonen vertrouwd_|**E-mail van mijn contactpersonen vertrouwen**|
|_Alleen TrustedLists_|**Vertrouw alleen e-mail van adressen in mijn lijst met veilige afzenders en domeinen en veilige mailinglijsten**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Verplaats e-mail van deze afzenders niet naar mijn map Ongewenste e-mail**|
|

<sup>\*</sup>**Toelichting :**

- In Exchange Online worden **domeinvermeldingen** in de lijst Veilige afzenders of de parameter _TrustedSendersAndDomains_ niet herkend, dus gebruik alleen e-mailadressen. In standalone EOP met adreslijstsynchronisatie worden domeinvermeldingen niet standaard gesynchroniseerd, maar u synchronisatie voor domeinen inschakelen. Zie [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)voor meer informatie.

- U de lijst Veilige geadresseerden niet rechtstreeks wijzigen met de cmdlet **Set-MailboxJunkEmailConfiguration** (de parameter _TrustedRecipientsAndDomains_ werkt niet). U wijzigt de lijst Veilige afzenders en deze wijzigingen worden gesynchroniseerd met de lijst Veilige geadresseerden.

Als u de safelist-verzameling in een postvak wilt configureren, gebruikt u de volgende syntaxis:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Als u meerdere waarden wilt invoeren en bestaande vermeldingen voor de parameters _BlockedSendersAndDomains_ en `"<Value1>","<Value2>"...` _TrustedSendersAndDomains_ wilt overschrijven, gebruikt u de volgende syntaxis: . Als u een of meer waarden wilt toevoegen of verwijderen zonder dat dit gevolgen heeft voor andere bestaande vermeldingen, gebruikt u de volgende syntaxis:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In dit voorbeeld worden de volgende instellingen geconfigureerd voor de safelist-verzameling in het postvak van Ori Epstein:

- Voeg de waarde shopping@fabrikam.com toe aan de lijst Geblokkeerde afzenders.

- Verwijder de waarde chris@fourthcoffee.com uit de lijst Veilige afzenders en de lijst Veilige geadresseerden.

- Hiermee configureert u contactpersonen in de map Contactpersonen om te worden behandeld als vertrouwde afzenders.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In dit voorbeeld wordt het domein contoso.com verwijderd uit de lijst Geblokkeerde afzenders in alle gebruikerspostvakken in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Zie [Set-MailboxJunkEmailConfiguration voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)gedetailleerde syntaxis- en parametergegevens.

 **Opmerkingen**:

- Als de gebruiker zijn postvak nooit heeft geopend, ontvangt u mogelijk een foutmelding wanneer u de vorige opdrachten uitvoert. Als u deze fout voor `-ErrorAction SlientlyContinue` bulkbewerkingen wilt onderdrukken, voegt u toe aan de opdracht **Set-MailboxJunkEmailConfiguration.**

- Zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak, u de safelistverzameling nog steeds configureren en het filter ongewenste e-mail van Outlook berichten verplaatsen naar het Postvak in of de map Ongewenste e-mail. Zie de instellingen [voor ongewenste e-mail in de](#about-junk-email-settings-in-outlook) sectie Outlook in dit onderwerp voor meer informatie.

- Het outlook-filter voor ongewenste e-mail heeft extra instellingen voor het verzamelen van safelist (bijvoorbeeld **Automatisch mensen toevoegen die ik e-mail aan de lijst Met veilige afzenders).** Zie [Filters voor ongewenste e-mail gebruiken gebruiken om te bepalen welke berichten u ziet.](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de safelist-verzameling in een postvak hebt geconfigureerd, gebruikt u een van de volgende procedures:

- Vervang _ \<PostvakIdentiteit\> _ door de naam, alias of e-mailadres van het postvak en voer de volgende opdracht uit om de eigenschapswaarden te verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Als de lijst met waarden te lang is, gebruikt u de onderstaande syntaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Informatie over instellingen voor ongewenste e-mail in Outlook

Als u de instellingen voor ongewenste e-mailfilter aan de clientzijde wilt inschakelen, uitschakelen en configureren die beschikbaar zijn in Outlook, gebruikt u Groepsbeleid. Zie [AdMX/ADML (Beheersjabloonbestanden) en Office Customization Tool voor Microsoft 365 Apps voor bedrijven, Office 2019 en Office 2016 voor](https://www.microsoft.com/download/details.aspx?id=49030)meer informatie.

Wanneer het Outlook Junk Email Filter is ingesteld op de standaardwaarde Geen **Junk** \> **automatische filtering** in **opties**voor ongewenste **e-mail** \> voor **thuis,** \> probeert Outlook massages niet te classificeren als spam, maar gebruikt het nog steeds de safelist-verzameling (de lijst Veilige afzenders, lijst Met veilige geadresseerden en de lijst Geblokkeerde afzenders) om berichten na levering naar de map Ongewenste e-mail te verplaatsen. Zie Overzicht van het [filter ongewenste e-mail](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)voor meer informatie over deze instellingen .

Wanneer het filter voor ongewenste e-mail van Outlook is ingesteld op **Laag** of **Hoog,** gebruikt het Filter ongewenste e-mail van Outlook zijn eigen SmartScreen-filterom spam te identificeren en naar de map Ongewenste e-mail te verplaatsen. Deze spamclassificatie staat los van het spamvertrouwensniveau (SCL) dat door EOP wordt bepaald. In feite negeert Outlook de SCL van EOP (tenzij EOP het bericht heeft gemarkeerd om spamfilters over te slaan) en gebruikt het zijn eigen criteria om te bepalen of het bericht spam is. Natuurlijk is het mogelijk dat de spam uitspraak van EOP en Outlook hetzelfde zou kunnen zijn. Zie Het [beschermingsniveau wijzigen in het filter ongewenste e-mail voor](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)meer informatie over deze instellingen.

> [!NOTE]
> In november 2016 stopte Microsoft met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen spam definities werden overgelaten op zijn plaats, maar hun effectiviteit zal waarschijnlijk degraderen na verloop van tijd. Zie [Ondersteuning voor SmartScreen in Outlook en Exchange voor](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)meer informatie.

Het Outlook Junk Email Filter kan dus de safelist-verzameling van het postvak en de eigen spamclassificatie gebruiken om berichten naar de map Ongewenste e-mail te verplaatsen, zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak.

Outlook en de webversie van Outlook ondersteunen beide de safelist-verzameling. De safelist-verzameling wordt opgeslagen in het postvak Exchange Online, zodat wijzigingen in de safelist-verzameling in Outlook worden weergegeven in de webversie van Outlook en vice versa.
