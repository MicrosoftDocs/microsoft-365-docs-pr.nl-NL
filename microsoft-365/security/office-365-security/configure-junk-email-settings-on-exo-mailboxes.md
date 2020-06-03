---
title: Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken
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
description: Beheerders kunnen leren hoe u de instellingen voor ongewenste e-mail configureert in Exchange Online-postvakken. Veel van deze instellingen zijn beschikbaar voor gebruikers in Outlook of Outlook in de webversie.
ms.openlocfilehash: 40364db9d4af9e093d8f2f74ee3c0f0373b1671a
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498661"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken

In Microsoft 365-organisaties met mailboxen in Exchange Online worden de instellingen voor antispam van organisaties beheerd door Exchange Online Protection (EOP). Zie [Antispambeveiliging in EOP](anti-spam-protection.md)voor meer informatie.

Maar er zijn ook specifieke antispaminstellingen die beheerders kunnen configureren op afzonderlijke postvakken in Exchange Online:

- **De regel voor ongewenste e-mail in- of uitschakelen:** de regel voor ongewenste e-mail is een verborgen regel voor postvak IN met de naam Ongewenste e-mailregel die standaard is ingeschakeld in elk postvak. De regel voor ongewenste e-mail bepaalt de volgende functies:

  - **Berichten verplaatsen naar de map Ongewenste e-mail op basis van antispambeleid:** Wanneer een antispambeleid is geconfigureerd met de actie **Bericht verplaatsen naar de map Ongewenste e-mail** voor een oordeel over het filteren van spam, wordt het bericht verplaatst naar de map Ongewenste e-mail nadat het bericht in het postvak is bezorgd. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor meer informatie over het filteren van spam in antispambeleid. Als zap (ZERO-hour auto purge) vaststelt dat een geleverd bericht spam of phish is, wordt het bericht met de filterregel ongewenste e-mail verplaatst naar de map Ongewenste e-mail voor **Bericht verplaatsen naar ongewenste e-mailmap** spamfilteringsuitslagen. Zie [Zero-hour auto purge (ZAP) in Exchange Online voor](zero-hour-auto-purge.md)meer informatie over ZAP.
  
  - **Instellingen voor ongewenste e-mail die gebruikers zelf configureren in Outlook of Outlook op de web:** De _safelist-verzameling_ is de lijst Veilige afzenders, de lijst Veilige geadresseerden en de lijst Afzenders blokkeren in elk postvak. De vermeldingen in deze lijsten bepalen of de regel voor ongewenste e-mail het bericht verplaatst naar het postvak IN of de map Ongewenste e-mail. Gebruikers kunnen de safelist-verzameling voor hun eigen postvak configureren in Outlook of Outlook op de web (voorheen Outlook Web App genoemd). Beheerders kunnen de safelist-verzameling configureren in het postvak van elke gebruiker.

Wanneer de regel voor ongewenste e-mail is ingeschakeld in het postvak, kan EOP berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie voor het filteren van **spam-regels Bericht verplaatsen naar map Ongewenste e-mail** of de lijst Afzenders blokkeren in het postvak, en voorkomen dat berichten worden bezorgd in de map Ongewenste e-mail (op basis van de lijst Veilige afzenders in het postvak).

 Wanneer de regel voor ongewenste e-mail is uitgeschakeld in het postvak, kan EOP geen berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie voor het filteren van **spam-regels Bericht verplaatsen naar map Ongewenste e-mail** of de safelistverzameling in het postvak.

Beheerders kunnen Exchange Online PowerShell gebruiken om de status van de regel voor ongewenste e-mail in postvakken uit te schakelen, in te schakelen en te bekijken. Beheerders kunnen Exchange Online PowerShell ook gebruiken om vermeldingen in de kluisverzameling op postvakken te configureren (de lijst Met veilige afzenders, de lijst Veilige geadresseerden en de lijst Afzenders blokkeren).

> [!NOTE]
> Berichten van afzenders die gebruikers hebben toegevoegd aan hun eigen lijsten met veilige afzenders, slaan verbindingsfiltering over als onderdeel van EOP (de SCL is -1). Als u wilt voorkomen dat gebruikers vermeldingen toevoegen aan hun lijst met veilige afzenders in Outlook, gebruikt u groepsbeleid zoals vermeld in de [sectie Over ongewenste e-mail in Outlook,](#about-junk-email-settings-in-outlook) later in dit onderwerp. Beleidsfiltering, Content filtering en Advanced Threat Protection (ATP) controles worden nog steeds toegepast op de berichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U Exchange Online PowerShell alleen gebruiken om deze procedures uit te voeren. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen toegewezen krijgen voordat u deze procedures uitvoeren. U hebt in het bijzonder de rol **E-mailontvangers** (die standaard is toegewezen aan de rolgroepen **Organisatiebeheer,** **Organisatiebeheer**en **Aangepaste e-mailontvangers)** of de rol **Gebruikersopties** (die standaard is toegewezen aan de rolgroepen **Organisatiebeheer** en **Helpdesk)** nodig. Zie [Rolgroepen wijzigen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)als u gebruikers wilt toevoegen aan rolgroepen in Exchange Online. Houd er rekening mee dat een gebruiker met standaardmachtigingen dezelfde procedures kan uitvoeren op zijn eigen postvak, zolang deze toegang heeft [tot Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- Veilige afzenders voor gedeelde postvakken worden niet gesynchroniseerd met Azure AD en EOP by design.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell gebruiken om de regel voor ongewenste e-mail in een postvak in te schakelen of uit te schakelen

> [!NOTE]
> U de cmdlet **Set-MailboxJunkEmailConfiguration** alleen gebruiken om de regel voor ongewenste e-mail uit te schakelen in een postvak dat is geopend in Outlook (in de exchange-modus in cache) of de webversie van Outlook. Als het postvak niet is geopend, ontvangt u de foutmelding: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` Als u deze fout voor bulkbewerkingen wilt onderdrukken, u toevoegen aan de opdracht `-ErrorAction SlientlyContinue` **Set-MailboxJunkEmailConfiguration.**

Als u de regel voor ongewenste e-mail in een postvak wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In dit voorbeeld wordt de regel voor ongewenste e-mail op de mailbox van Ori Epstein uitgeschakeld.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In dit voorbeeld wordt de regel voor ongewenste e-mail uitgeschakeld voor alle postvakken van gebruikers in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Zie [Set-MailboxJunkEmailConfiguration voor](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)gedetailleerde syntaxis- en parametergegevens .

> [!NOTE]
> 
> - Als de gebruiker zijn postvak nooit heeft geopend, ontvangt u mogelijk een foutmelding wanneer u de vorige opdracht uitvoert. Als u deze fout voor bulkbewerkingen wilt onderdrukken, voegt u de `-ErrorAction SlientlyContinue` opdracht **Set-MailboxJunkEmailConfiguration toe aan de opdracht Set-MailboxJunkEmailConfiguration.**
> 
> - Zelfs als u de regel voor ongewenste e-mail uitschakelt, kan het Outlook-filter voor ongewenste e-mail (afhankelijk van hoe het is geconfigureerd) ook bepalen of een bericht spam is en berichten verplaatsen naar de map Postvak IN of Ongewenste e-mail op basis van het eigen spam-vonnis en de verzameling van de safelist in het postvak. Zie de sectie [Over ongewenste e-mail in Outlook in](#about-junk-email-settings-in-outlook) dit onderwerp voor meer informatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de regel voor ongewenste e-mail in een postvak hebt ingeschakeld of uitgeschakeld, gebruikt u een van de volgende procedures:

- Vervang _\<MailboxIdentity\>_ de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om de waarde van de **eigenschap Ingeschakeld** te verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell gebruiken om de safelist-verzameling op een postvak te configureren

De safelist-verzameling in een postvak bevat de lijst Veilige afzenders, de lijst Veilige geadresseerden en de lijst Met geblokkeerde afzenders. Standaard kunnen gebruikers de safelist-verzameling configureren in hun eigen postvak in Outlook of outlook in de web. Beheerders kunnen de bijbehorende parameters op de **cmdlet Set-MailboxJunkEmailConfiguration** gebruiken om de safelist-verzameling op het postvak van een gebruiker te configureren. Deze parameters worden beschreven in de volgende tabel.

|||
|---|---|
|**Parameter op Set-MailboxJunkEmailConfiguratie**|**Webinstelling van Outlook**|
|_GeblokkeerdeSendersAndDomains_|**E-mail van deze afzenders of domeinen verplaatsen naar mijn map Ongewenste e-mail**|
|_Contactpersonenvertrouwen_|**E-mail van mijn contactpersonen vertrouwen**|
|_TrustedListsOnly_|**Vertrouw alleen e-mailadressen van adressen in mijn lijst met veilige afzenders en domeinen en veilige mailinglijsten**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Verplaats e-mail van deze afzenders niet naar mijn map Ongewenste e-mail**|
|

<sup>\*</sup>**Toelichting :**

- In Exchange Online worden **domeinvermeldingen** in de lijst Veilige afzenders of de parameter _TrustedSendersAndDomains_ niet herkend, dus gebruik alleen e-mailadressen. In standalone EOP met adreslijstsynchronisatie worden domeinvermeldingen niet standaard gesynchroniseerd, maar u synchronisatie voor domeinen inschakelen. Zie [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)voor meer informatie.

- U de lijst Veilige geadresseerden niet rechtstreeks wijzigen met de cmdlet **Set-MailboxJunkEmailConfiguration** (de parameter _TrustedRecipientsAndDomains_ werkt niet). U wijzigt de lijst Met veilige afzenders en deze wijzigingen worden gesynchroniseerd met de lijst Veilige geadresseerden.

Als u de safelist-verzameling in een postvak wilt configureren, gebruikt u de volgende syntaxis:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Als u meerdere waarden wilt invoeren en bestaande vermeldingen voor de parameters _BlockedSendersAndDomains_ en _TrustedSendersAndDomains_ wilt overschrijven, gebruikt u de volgende syntaxis: `"<Value1>","<Value2>"...` . Als u een of meer waarden wilt toevoegen of verwijderen zonder dat dit gevolgen heeft voor andere bestaande vermeldingen, gebruikt u de volgende syntaxis:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In dit voorbeeld worden de volgende instellingen geconfigureerd voor de safelist-verzameling op het postvak van Ori Epstein:

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

Zie [Set-MailboxJunkEmailConfiguration voor](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)gedetailleerde syntaxis- en parametergegevens .

> [!NOTE]
> 
> - Als de gebruiker zijn postvak nooit heeft geopend, ontvangt u mogelijk een foutmelding wanneer u de vorige opdrachten uitvoert. Als u deze fout voor bulkbewerkingen wilt onderdrukken, voegt u de `-ErrorAction SlientlyContinue` opdracht **Set-MailboxJunkEmailConfiguration toe aan de opdracht Set-MailboxJunkEmailConfiguration.**
> 
> - Zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak, u de verzameling van de safelist nog steeds configureren en kan het filter Ongewenste e-mail van Outlook berichten verplaatsen naar het postvak IN of de map Ongewenste e-mail. Zie de sectie [Over ongewenste e-mail in Outlook in](#about-junk-email-settings-in-outlook) dit onderwerp voor meer informatie.
> 
> - Het Filter ongewenste e-mail van Outlook heeft extra instellingen voor het verzamelen van safelists (voeg bijvoorbeeld **automatisch mensen toe die ik e-mail aan de lijst Veilige afzenders).** Zie [Filters voor ongewenste e-mail gebruiken om te bepalen welke berichten u ziet](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)voor meer informatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de safelist-verzameling in een postvak hebt geconfigureerd, gebruikt u een van de volgende procedures:

- Vervang _\<MailboxIdentity\>_ de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om de eigenschapswaarden te verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Als de lijst met waarden te lang is, gebruikt u deze syntaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Informatie over instellingen voor ongewenste e-mail in Outlook

Als u de instellingen voor ongewenste e-mailfilter aan de clientzijde die beschikbaar zijn in Outlook, wilt in- en configureren, gebruikt u Groepsbeleid. Zie [Instellingen voor beheerderssjabloonbestanden (ADMX/ADML) en Office Customization Tool voor Microsoft 365 Apps voor bedrijven, Office 2019 en Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) en [Instellingen voor ongewenste e-mail implementeren, zoals de lijst Veilige afzenders, voor](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi)meer informatie met groepsbeleid.

Wanneer het Outlook-filter voor ongewenste e-mail is ingesteld op de standaardwaarde **Geen automatische filtering** in opties voor ongewenste e-mailopties **voor** ongewenste \> **Junk** \> **e-mail** \> **Options**thuis, probeert Outlook massages niet te classificeren als spam, maar gebruikt u nog steeds de safelist-verzameling (de lijst Met veilige afzenders, lijst Met veilige geadresseerden en lijst Met geblokkeerde afzenders) om berichten na levering naar de map Ongewenste e-mail te verplaatsen. Zie Overzicht van het [filter ongewenste e-mail](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)voor meer informatie over deze instellingen.

Wanneer het filter ongewenste e-mail van Outlook is ingesteld **op Laag** of **Hoog,** gebruikt het filter Ongewenste e-mail van Outlook zijn eigen SmartScreen-filtertechnologie om spam te identificeren en te verplaatsen naar de map Ongewenste e-mail. Deze spamclassificatie staat los van het spamvertrouwensniveau (SCL) dat wordt bepaald door EOP. In feite negeert Outlook de SCL van EOP (tenzij EOP het bericht heeft gemarkeerd om spamfiltering over te slaan) en gebruikt het zijn eigen criteria om te bepalen of het bericht spam is. Natuurlijk is het mogelijk dat de spam uitspraak van EOP en Outlook hetzelfde zou kunnen zijn. Zie [Het beschermingsniveau wijzigen in het filter ongewenste e-mail wijzigen](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)voor meer informatie over deze instellingen.

> [!NOTE]
> In november 2016 is Microsoft gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen spam definities werden achtergelaten op zijn plaats, maar hun effectiviteit zal waarschijnlijk degraderen na verloop van tijd. Zie [Ondersteuning voor SmartScreen deprecating in Outlook en Exchange voor](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)meer informatie.

Het filter ongewenste e-mail van Outlook kan dus de safelist-verzameling van het postvak en de eigen spamclassificatie gebruiken om berichten naar de map Ongewenste e-mail te verplaatsen, zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak.

Outlook en Outlook op de web ondersteunen beide de safelist-verzameling. De safelist-verzameling wordt opgeslagen in het Exchange Online-postvak, zodat wijzigingen in de safelist-verzameling in Outlook in de web en vice versa worden weergegeven.

## <a name="limits-for-junk-email-settings"></a>Limieten voor instellingen voor ongewenste e-mail

De safelist-verzameling (de lijst Met veilige afzenders, lijst met veilige geadresseerden en lijst met geblokkeerde afzenders) die is opgeslagen in het postvak van de gebruiker, wordt ook gesynchroniseerd met EOP. Met adreslijstsynchronisatie wordt de safelist-verzameling gesynchroniseerd met Azure AD.

- De safelist verzameling in het postvak van de gebruiker heeft een limiet van 510 KB, die alle lijsten bevat, plus extra ongewenste e-mail filterinstellingen. Als een gebruiker deze limiet overschrijdt, ontvangt hij/zij een Outlook-fout die er als volgt uitziet:

  > Kan/kan niet worden toegevoegd aan de e-maillijsten van de server. U bent meer dan de grootte toegestaan op de server. Het filter Ongewenste e-mail op de server wordt uitgeschakeld totdat uw ongewenste e-maillijsten zijn teruggebracht tot de grootte die door de server is toegestaan.

  Zie [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)voor meer informatie over deze limiet en hoe u deze wijzigen.

- De gesynchroniseerde safelist verzameling in EOP heeft de volgende synchronisatielimieten:

  - 1024 totaalvermeldingen in de lijst Veilige afzenders, de lijst Veilige geadresseerden en externe contactpersonen als **e-mail vertrouwen van mijn contactpersonen** is ingeschakeld.
  - 500 in totaal vermeldingen in de lijst Geblokkeerde afzenders en Geblokkeerde domeinen.

  Wanneer de 1024-instaplimiet is bereikt, gebeuren de volgende dingen:
  
  - De lijst stopt met het accepteren van items in PowerShell en Outlook op het web, maar er wordt geen fout weergegeven.

    Outlook-gebruikers kunnen meer dan 1024-vermeldingen blijven toevoegen totdat ze de Outlook-limiet van 510 KB hebben bereikt. Outlook kan deze extra vermeldingen gebruiken, zolang een EOP-filter het bericht niet blokkeert voordat het aan het postvak wordt bezorgd (regels voor e-mailstroom, anti-spoofing, enz.).

- Met adreslijstsynchronisatie worden de vermeldingen in de volgende volgorde gesynchroniseerd met Azure AD:

  1. **E-mailcontactpersonen als e-mail vertrouwen van mijn contactpersonen** is ingeschakeld.
  2. De lijst met veilige afzenders en de lijst veilige geadresseerden worden gecombineerd, gedupliceerd en alfabetisch gesorteerd wanneer er een wijziging wordt aangebracht voor de eerste 1024-vermeldingen.

  De eerste 1024 vermeldingen worden gebruikt en relevante informatie wordt gestempeld in de berichtkoppen.
  
  Items van meer dan 1024 die niet zijn gesynchroniseerd met Azure AD, worden verwerkt door Outlook (niet outlook op de web) en er wordt geen informatie gestempeld in de berichtkoppen.

Zoals u zien, vermindert het inschakelen van de **e-mail Vertrouwen vanuit mijn contactpersoneninstelling** het aantal veilige afzenders en veilige geadresseerden dat kan worden gesynchroniseerd. Als dit een probleem is, raden we u aan groepsbeleid te gebruiken om deze functie uit te schakelen:

- Bestandsnaam: outlk16.opax
- Beleidsinstelling: **E-mail vertrouwen van contactpersonen**
