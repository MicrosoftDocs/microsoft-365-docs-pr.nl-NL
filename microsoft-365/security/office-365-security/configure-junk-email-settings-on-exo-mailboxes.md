---
title: Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen de instellingen voor ongewenste e-mail in postvakken van Exchange Online leren configureren. Veel van deze instellingen zijn beschikbaar voor gebruikers in Outlook of de webversie van Outlook.
ms.openlocfilehash: 632c6f37b80cdc38b513f66ad42e4a5c25b41f25
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203345"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online worden de antispam instellingen voor de organisatie bestuurd via Exchange Online Protection (EOP). Zie [bescherming tegen spam in EOP](anti-spam-protection.md)voor meer informatie.

Er zijn ook specifieke antispam instellingen die beheerders kunnen configureren voor afzonderlijke postvakken in Exchange Online:

- **De regel voor ongewenste E-mail in-of uitschakelen**: de regel voor ongewenste e-mail is een verborgen regel voor het postvak in met de naam ongewenste e-mail regel die standaard is ingeschakeld in elk postvak. De regel voor ongewenste e-mail beheert de volgende functies:

  - **Berichten verplaatsen naar de map Ongewenste e-mail op basis van een antispam**beleid: wanneer een Antispambeleid is geconfigureerd met de **map actie verplaatsen naar de map Ongewenste** e-mail voor een spamfilter Verdict, wordt het bericht in de filterregel voor ongewenste e-mail verplaatst naar de map Ongewenste e-mail nadat het bericht in het postvak is bezorgd. Zie [Antispambeleid in EOP](configure-your-spam-filter-policies.md)voor meer informatie over het filteren van ongewenste e-mail Verdicts in antispambeleid. Ook als het automatisch wissen van nul (ZAP) een bezorgd bericht voor spam of phishing afneemt, verplaatst de regel voor het filter voor ongewenste e-mail het bericht naar de map Ongewenste E-mail voor het verplaatsen van een **bericht naar** de map Ongewenste e-mail voor ongewenste e-mail verdict-acties. Zie voor meer informatie over ZAP de rijen [automatisch wissen van nul (ZAP) in Exchange Online](zero-hour-auto-purge.md).

  - **Instellingen voor ongewenste e-mail die gebruikers zelf configureren in Outlook of de webversie van Outlook**: de _veilige lijst-verzameling_ is de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst afzenders blokkeren voor elk postvak. Met de vermeldingen in deze lijsten wordt bepaald of het bericht in de regel voor ongewenste e-mail naar het postvak in of de map Ongewenste E-mail wordt verplaatst. Gebruikers kunnen de veilige lijst-verzameling configureren voor hun eigen postvak in Outlook of de webversie van Outlook (voorheen Outlook Web app). Beheerders kunnen de veilige lijst-verzameling configureren voor het postvak van een gebruiker.

Wanneer de regel ongewenste e-mail is ingeschakeld in het postvak, kunnen berichten in EOP worden verplaatst naar de map Ongewenste E-mail op basis van de actie spam filteren Verdict, **bericht verplaatsen naar map Ongewenste e-mail** of de lijst met geblokkeerde afzenders in het postvak, en voorkomen dat berichten worden bezorgd in de map Ongewenste e-mail (op basis van de lijst met veilige afzenders in het Postvak).

 Wanneer de regel voor ongewenste e-mail in het postvak is uitgeschakeld, kunnen er geen berichten worden verplaatst naar de map Ongewenste e-mail op basis van het spamfilter verdict actie **bericht verplaatsen naar map Ongewenste e-mail** of de verzameling veilige lijst in het postvak.

Beheerders kunnen Exchange Online PowerShell gebruiken om de status van de regel voor ongewenste e-mail op postvakken uit te schakelen, in te schakelen en te bekijken. Beheerders kunnen ook Exchange Online PowerShell gebruiken voor het configureren van vermeldingen in de veilige lijst-verzameling in postvakken (de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst afzenders blokkeren).

> [!NOTE]
> Berichten van afzenders die gebruikers hebben toegevoegd aan hun eigen lijsten met veilige afzenders, worden gebruikt om het filteren van verbindingen over te slaan als onderdeel van EOP (de SCL is-1). Als u wilt voorkomen dat gebruikers items kunnen toevoegen aan hun lijst met veilige afzenders in Outlook, gebruikt u Groepsbeleid zoals vermeld in de sectie  [over instellingen voor ongewenste e-mail in Outlook](#about-junk-email-settings-in-outlook) verderop in dit onderwerp. Beleids filters voor beleids filters, het filteren van inhoud en de Advanced Threat Protection-controles worden op de berichten toegepast.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U kunt alleen Exchange Online PowerShell gebruiken om deze procedures uit te voeren. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen zijn toegewezen voordat u deze procedures kunt uitvoeren. Met name hebt u de rol van **e-mail geadresseerden** nodig (die standaard is toegewezen aan de rollen groepen **Organisatiebeheer**, **ontvanger**en **aangepaste e-mail geadresseerden** ) of de rol van **gebruikersopties** (die standaard zijn toegewezen aan de rollen groepen **Organisatiebeheer** en **Help Desk** . Zie [rollen groepen wijzigen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)voor informatie over het toevoegen van gebruikers aan rollen groepen in Exchange Online. Houd er rekening mee dat een gebruiker met standaardmachtigingen dezelfde procedures op hun eigen postvak kan uitvoeren, mits deze [toegang hebben tot Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).

- In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- Veilige afzenders voor gedeelde postvakken worden niet gesynchroniseerd met Azure AD en EOP op ontwerp.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell gebruiken om de regel voor ongewenste e-mail in een postvak in of uit te schakelen

> [!NOTE]
> U kunt alleen de **set-MailboxJunkEmailConfiguration** -cmdlet gebruiken om de regel voor ongewenste e-mail te deactiveren voor een postvak dat is geopend in Outlook (in de Exchange-modus met cache) of de webversie van Outlook. Als het postvak niet is geopend, krijgt u de foutmelding: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` Als u deze fout wilt onderdrukken voor bulkbewerkingen, kunt u deze toevoegen `-ErrorAction SilentlyContinue` aan de opdracht **set-MailboxJunkEmailConfiguration** .

Gebruik de volgende syntaxis om de regel voor ongewenste e-mail in een postvak in of uit te schakelen:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In dit voorbeeld wordt de regel voor ongewenste e-mail in het postvak van de ori-Epstein uitgeschakeld.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In dit voorbeeld wordt de regel voor ongewenste e-mail uitgeschakeld voor alle postvakken van gebruikers in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Zie [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)voor gedetailleerde syntaxis-en parameterinformatie.

> [!NOTE]
>
> - Als de gebruiker het postvak niet heeft geopend, wordt er mogelijk een fout weergegeven wanneer u de vorige opdracht uitvoert. Als u deze fout wilt onderdrukken voor bulkbewerkingen, voegt u deze toe `-ErrorAction SilentlyContinue` aan de opdracht **set-MailboxJunkEmailConfiguration** .
>
> - Ook als u de regel voor ongewenste e-mail uitschakelt, kan het filter voor ongewenste e-mail van Outlook (afhankelijk van de configuratie van het bestand) bepalen of een bericht spam bevat, en kan berichten naar het postvak in of de map Ongewenste E-mail verplaatsen op basis van de spam verdict en de veilige lijst-verzameling in het postvak. Zie voor meer informatie het artikel [over de instellingen voor ongewenste e-mail in Outlook](#about-junk-email-settings-in-outlook) in dit onderwerp.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga op een van de volgende manieren te werk om te controleren of de regel voor ongewenste e-mail is ingeschakeld of uitgeschakeld voor een postvak:

- Vervang door _\<MailboxIdentity\>_ de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om de **ingeschakelde** eigenschapswaarde te verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell gebruiken om de veilige lijst-verzameling te configureren voor een postvak

De veilige lijst-verzameling in een postvak bevat de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst met geblokkeerde afzenders. Gebruikers kunnen standaard de veilige lijst-verzameling configureren voor een eigen postvak in Outlook of de webversie van Outlook. Beheerders kunnen de bijbehorende parameters op de **set-MailboxJunkEmailConfiguration-** cmdlet gebruiken om de veilige lijst-verzameling in het postvak van een gebruiker te configureren. In de volgende tabel worden de volgende parameters beschreven.

****

|Parameter voor set-MailboxJunkEmailConfiguration|Instelling van de webversie van Outlook|
|---|---|
|_BlockedSendersAndDomains_|**E-mail van deze afzenders of domeinen naar de map Ongewenste E-mail verplaatsen**|
|_ContactsTrusted_|**E-mail van mijn contactpersonen vertrouwen**|
|_TrustedListsOnly_|**E-mail van adressen alleen vertrouwen in de lijsten met veilige afzenders en domeinen en de lijst met veilige adressen**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**E-mail van deze afzenders niet naar mijn map Ongewenste E-mail verplaatsen**|
|

<sup>\*</sup>**Opmerkingen**:

- In Exchange Online worden **domein vermeldingen** in de lijst met veilige afzenders of _TrustedSendersAndDomains_ niet herkend, dus gebruik alleen e-mailadressen. Bij zelfstandige EOP met adreslijstsynchronisatie worden domein vermeldingen niet standaard gesynchroniseerd, maar u kunt wel synchronisatie voor domeinen inschakelen. Zie [KB3019657](https://support.microsoft.com/help/3019657)voor meer informatie.

- U kunt de lijst met veilige geadresseerden niet rechtstreeks wijzigen met behulp van de cmdlet **set-MailboxJunkEmailConfiguration** (de parameter _TrustedRecipientsAndDomains_ werkt niet). U wijzigt de lijst met veilige afzenders en deze wijzigingen worden gesynchroniseerd met de lijst met veilige geadresseerden.

Gebruik de volgende syntaxis om de veilige lijst-verzameling te configureren voor een postvak:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Als u meerdere waarden wilt invoeren en de bestaande vermeldingen voor de parameters voor _BlockedSendersAndDomains_ en _TrustedSendersAndDomains_ wilt overschreven, gebruikt u de volgende syntaxis: `"<Value1>","<Value2>"...` . Gebruik de volgende syntaxis om een of meer waarden toe te voegen of te verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In dit voorbeeld worden de volgende instellingen geconfigureerd voor de veilige lijst-verzameling in het postvak van ori Epstein:

- Voeg de waarde shopping@fabrikam.com toe aan de lijst met geblokkeerde afzenders.

- Verwijder de waarde chris@fourthcoffee.com uit de lijst met veilige afzenders en de lijst met veilige geadresseerden.

- Hiermee worden contactpersonen in de map met contactpersonen geconfigureerd zodat ze als vertrouwde afzenders worden beschouwd.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In dit voorbeeld wordt de contoso.com van de lijst met geblokkeerde afzenders in alle gebruikerspostvakken van de organisatie verwijderd.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Zie [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)voor gedetailleerde syntaxis-en parameterinformatie.

> [!NOTE]
>
> - Als de gebruiker het postvak niet heeft geopend, wordt er mogelijk een fout weergegeven wanneer u de vorige opdrachten uitvoert. Als u deze fout wilt onderdrukken voor bulkbewerkingen, voegt u deze toe `-ErrorAction SilentlyContinue` aan de opdracht **set-MailboxJunkEmailConfiguration** .
>
> - Zelfs als de regel voor ongewenste e-mail is uitgeschakeld voor het postvak, kunt u de veilige lijst-verzameling nog steeds configureren, en het filter voor ongewenste E-mail van Outlook kan berichten naar het postvak in of de map Ongewenste E-mail verplaatsen. Zie voor meer informatie het artikel [over de instellingen voor ongewenste e-mail in Outlook](#about-junk-email-settings-in-outlook) in dit onderwerp.
>
> - Het filter voor ongewenste E-mail van Outlook bevat extra instellingen voor de veilige lijst-verzameling (bijvoorbeeld **automatisch e-mailberichten toevoegen aan de lijst met veilige afzenders**). Zie voor meer informatie de [filters voor ongewenste E-mail gebruiken om te bepalen welke berichten worden weer](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)gegeven.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Voer een van de volgende procedures uit om te controleren of u de veilige lijst-verzameling hebt geconfigureerd voor een postvak:

- Vervang door _\<MailboxIdentity\>_ de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om de eigenschapwaarden te controleren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Als de lijst met waarden te lang is, gebruikt u de volgende syntaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Instellingen voor ongewenste e-mail in Outlook

Als u de instellingen voor het filter voor ongewenste E-mail aan de clientzijde wilt inschakelen, uitschakelen en configureren, gebruikt u Groepsbeleid. Zie voor meer informatie [Administrative template files (ADMX/ADML) en Office Customization Tool voor Microsoft 365-apps voor Enterprise, office 2019 en office 2016](https://www.microsoft.com/download/details.aspx?id=49030) en [hoe u instellingen voor ongewenste e-mail, zoals de lijst met veilige afzenders, via Groepsbeleid](https://support.microsoft.com/help/2252421).

Wanneer het filter voor ongewenste **e-mail van Outlook** is ingesteld op de standaardwaarde in de opties voor het uitschakelen **van ongewenste e-mail** in \> **Junk** \> **Junk E-Mail Options** \> **Options**Outlook, wordt niet geprobeerd massages te classificeren als spam, maar wordt de veilige lijst-verzameling (de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst met geblokkeerde afzenders) gebruikt om berichten te verplaatsen naar de map Ongewenste e-mail na levering. Zie [overzicht van het filter voor ongewenste e-mail](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)voor meer informatie over deze instellingen.

Wanneer het filter voor ongewenste e-mail van Outlook is ingesteld op **slecht** of **hoog**, gebruikt het filter voor ongewenste e-mail van Outlook een eigen versie van het filter om ongewenste e-mail te identificeren en te verplaatsen naar de map Ongewenste e-mail. Deze categorie voor ongewenste e-mail is losstaat van het spam betrouwbaarheidsniveau (SCL) dat wordt bepaald door EOP. In feite negeert Outlook de SCL van EOP (tenzij EOP het bericht heeft gemarkeerd om spam te filteren) en worden de eigen criteria gebruikt om te bepalen of het bericht spam bevat. U kunt natuurlijk natuurlijk ook de spam verdict van EOP en Outlook. Zie [het beschermingsniveau voor ongewenste E-mail wijzigen](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)voor meer informatie over deze instellingen.

> [!NOTE]
> In november 2016 hebben Microsoft geen updates van de definities van spam updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande definities voor de SmartScreen-spam werden weggegaan, maar de effectiviteit ervan is waarschijnlijk slecht. Voor meer informatie raadpleegt u ondersteuning voor het weergeven van [ondersteuning voor SmartScreen in Outlook en Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Het filter voor ongewenste E-mail van Outlook kan de veilige lijst-verzameling van het postvak en de afzonderlijke indeling voor ongewenste e-mail gebruiken voor het verplaatsen van berichten naar de map Ongewenste E-mail, zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak.

De webversie van Outlook en de webversie van Outlook biedt ondersteuning voor de veilige lijst-verzameling. De veilige lijst-verzameling wordt opgeslagen in het postvak van Exchange Online, dus wijzigingen in de veilige lijst-verzameling in Outlook worden weergegeven in de webversie van Outlook, en omgekeerd.

## <a name="limits-for-junk-email-settings"></a>Limieten voorinstellingen voor ongewenste e-mail

De verzameling veilige lijst (de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst met geblokkeerde afzenders) die zijn opgeslagen in het postvak van de gebruiker, wordt ook gesynchroniseerd met EOP. Met adreslijstsynchronisatie wordt de veilige lijst-verzameling gesynchroniseerd met Azure AD.

- De veilige lijst-verzameling in het postvak van de gebruiker heeft een limiet van 510 KB, dit omvat alle lijsten, plus aanvullende instellingen voor het filter voor ongewenste e-mail. Als een gebruiker deze limiet overschrijdt, wordt er een Outlook-fout weergegeven die er als volgt uitziet:

  > Kan/kan niet worden toegevoegd aan de lijsten voor ongewenste E-mail van de server. U hebt de grootte van de server overschreden. Het filter voor ongewenste E-mail op de server wordt uitgeschakeld totdat uw lijsten met ongewenste E-mail zijn beperkt tot de grootte die door de server is toegestaan.

  Zie [KB2669081](https://support.microsoft.com/help/2669081)voor meer informatie over deze limiet en hoe u deze kunt wijzigen.

- De gesynchroniseerde veilige lijst-verzameling in EOP heeft de volgende synchronisatie beperkingen:

  - 1024 totale vermeldingen in de lijst met veilige afzenders, de lijst met veilige geadresseerden en externe contactpersonen als de functie **e-mail van mijn contactpersonen vertrouwen** is ingeschakeld.
  - 500 totale vermeldingen in de lijst met geblokkeerde afzenders en geblokkeerde domeinen.

  Wanneer de 1024-invoer limiet is bereikt, gebeurt het volgende:

  - In de lijst worden geen vermeldingen geaccepteerd in PowerShell en de webversie van Outlook, maar er wordt geen foutbericht weergegeven.

    Outlook-gebruikers kunnen meer dan 1024-vermeldingen toevoegen totdat ze de Outlook-limiet van 510 KB bereiken. In Outlook kunnen deze extra vermeldingen worden gebruikt, zolang een EOP-filter het bericht niet blokkeert voordat het wordt bezorgd in het postvak (e-mail stroom regels, anti-spoofing, enzovoort).

- Met adreslijstsynchronisatie worden de vermeldingen in de volgende volgorde gesynchroniseerd met Azure AD:

  1. Contactpersonen verzenden als **e-mail van mijn contactpersonen vertrouwen** is ingeschakeld.
  2. De lijst met veilige afzenders en lijst met veilige geadresseerden worden gecombineerd, opnieuw gedupliceerd en alfabetisch gesorteerd wanneer een wijziging wordt aangebracht voor de eerste 1024-vermeldingen.

  De eerste 1024-vermeldingen worden gebruikt en de relevante informatie wordt in de berichtkoppen vastgelegd.

  Vermeldingen via 1024 die niet zijn gesynchroniseerd met Azure AD, worden verwerkt door Outlook (niet in de webversie van Outlook) en er worden geen gegevens in de berichtkoppen weergegeven.

Zoals u ziet, is het mogelijk dat de instelling **e-mail van mijn contactpersonen vertrouwen** het aantal veilige afzenders en veilige geadresseerden die kan worden gesynchroniseerd, reduceert. Als dit het geval is, is het raadzaam om Groepsbeleid te gebruiken om deze functie uit te schakelen:

- Bestandsnaam: outlk16. opax
- Beleidsinstelling: **e-mail van contactpersonen vertrouwen**
