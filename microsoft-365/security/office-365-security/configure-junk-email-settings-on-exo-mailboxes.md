---
title: Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het configureren van de instellingen voor ongewenste e-mail in postvakken van Exchange Online. Veel van deze instellingen zijn beschikbaar voor gebruikers in Outlook of de webversie van Outlook.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2aa75376a431ded5abf44ad17ddad4f0ac731fa8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165689"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-organisaties met postvakken in Exchange Online worden de antispaminstellingen van de organisatie beheerd door Exchange Online Protection (EOP). Zie Beveiliging [tegen ongewenste e-mail in EOP voor meer informatie.](anti-spam-protection.md)

Maar er zijn ook specifieke antispaminstellingen die beheerders voor afzonderlijke postvakken in Exchange Online kunnen configureren:

- **De regel voor ongewenste** e-mail in- of uitschakelen: de regel voor ongewenste e-mail is een verborgen regel voor Postvak IN met de naam Regel voor ongewenste e-mail. Deze regel is standaard ingeschakeld in elk postvak. Met de regel voor ongewenste e-mail worden de volgende functies bepaald:

  - Verplaats berichten naar de map Ongewenste e-mail op basis van antispambeleid: wanneer een antispambeleid is geconfigureerd met de actie Bericht verplaatsen naar de map Ongewenste e-mail voor een filter voor ongewenste e-mail, wordt het bericht met de filterregel voor ongewenste e-mail verplaatst naar de map Ongewenste **e-mail** nadat het bericht in het postvak is bezorgd.  Zie Antispambeleid configureren in EOP voor meer informatie over spamfilters [in antispambeleid.](configure-your-spam-filter-policies.md) En als door Auto Purge (ZAP) van nul uur wordt bepaald dat een bezorgd bericht spam of  phish is, verplaatst de regel voor het filteren van ongewenste e-mail het bericht naar de map Ongewenste e-mail voor Bericht verplaatsen naar spamfilteracties in de map Ongewenste e-mail. Zie [Zero-hour Auto Purge (ZAP) in Exchange Online voor meer](zero-hour-auto-purge.md)informatie over ZAP.

  - Instellingen voor ongewenste e-mail die gebruikers voor zichzelf **configureren in Outlook** of de webversie van Outlook: de lijst met veilige afzenders is de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst met geblokkeerde afzenders voor elk postvak.  Aan de vermeldingen in deze lijsten wordt bepaald of het bericht met de regel voor ongewenste e-mail wordt verplaatst naar het Postvak IN of naar de map Ongewenste e-mail. Gebruikers kunnen de safelistverzameling configureren voor hun eigen postvak in Outlook of de webversie van Outlook (voorheen Outlook Web App). Beheerders kunnen de safelistverzameling configureren in het postvak van een gebruiker.

Wanneer de regel voor ongewenste e-mail is ingeschakeld in het postvak, kan EOP  berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie spamfilter Bericht verplaatsen naar de map Ongewenste e-mail of de lijst met geblokkeerde afzenders in het postvak en voorkomen dat berichten worden bezorgd in de map Ongewenste e-mail (op basis van de lijst met veilige afzenders in het postvak).

 Wanneer de regel voor ongewenste e-mail is uitgeschakeld in het postvak, kan EOP  geen berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie spamfilter bericht verplaatsen naar de map Ongewenste e-mail of de safelistverzameling in het postvak.

Beheerders kunnen Exchange Online PowerShell gebruiken om de status van de regel voor ongewenste e-mail voor postvakken uit te schakelen, in te schakelen en te bekijken. Beheerders kunnen ook Exchange Online PowerShell gebruiken om vermeldingen in de lijst met veilige afzenders (de lijst met veilige afzenders, de lijst met veilige geadresseerden en de lijst met geblokkeerde afzenders) te configureren.

> [!NOTE]
> Berichten van afzenders die gebruikers hebben toegevoegd aan hun eigen lijst Veilige afzenders, slaan verbindingsfilters over als onderdeel van EOP (de SCL is -1). Als u wilt voorkomen dat gebruikers vermeldingen toevoegen aan hun lijst met veilige afzenders in Outlook, gebruikt u Groepsbeleid zoals wordt vermeld in de instellingen voor over ongewenste  [e-mail in outlook](#about-junk-email-settings-in-outlook) verder op dit artikel. Beleidsfiltering, inhoudsfiltering en Defender voor Office 365-controles blijven van toepassing op de berichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U kunt alleen Exchange Online PowerShell gebruiken om de procedures in dit artikel uit te voeren. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen toegewezen krijgen in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol E-mailontvangers nodig (die standaard is toegewezen aan de  rollengroepen Organisatiebeheer, Geadresseerdenbeheer  en  Aangepaste  **e-mailontvangers)** of Gebruikersopties (die standaard is toegewezen aan de rollengroepen Organisatiebeheer en Helpdesk).  Zie Rollengroepen wijzigen in Exchange Online als u gebruikers wilt toevoegen aan [rollengroepen in Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) Gebruikers met standaardmachtigingen kunnen dezelfde procedures uitvoeren voor hun eigen postvak, zolang ze toegang hebben tot [Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- Veilige afzenders voor gedeelde postvakken worden niet automatisch gesynchroniseerd met Azure AD en EOP.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell gebruiken om de regel voor ongewenste e-mail in een postvak in of uit te schakelen

> [!NOTE]
> U kunt alleen de cmdlet **Set-MailboxJunkEmailConfiguration** gebruiken om de regel voor ongewenste e-mail uit te schakelen voor een postvak dat is geopend in Outlook (in de Exchange-modus met cache) of de webversie van Outlook. Als het postvak niet is geopend, wordt het foutbericht weergegeven: Als u deze fout bij bulkbewerkingen wilt onderdrukken, kunt u toevoegen aan de opdracht `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration.**

Gebruik de volgende syntaxis om de regel voor ongewenste e-mail in een postvak in of uit te schakelen:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In dit voorbeeld wordt de regel voor ongewenste e-mail in het postvak van Ori Epstein uitgeschakeld.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In dit voorbeeld wordt de regel voor ongewenste e-mail uitgeschakeld voor alle gebruikerspostvakken in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Zie [Set-MailboxJunkEmailConfiguration voor](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)gedetailleerde syntaxis- en parameterinformatie.

> [!NOTE]
>
> - Als de gebruiker het postvak nog nooit heeft geopend, kan er een fout worden weergegeven wanneer u de vorige opdracht hebt uitgevoerd. Als u deze fout bij bulkbewerkingen wilt onderdrukken, voegt u de opdracht `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** toe.
>
> - Zelfs als u de regel voor ongewenste e-mail uit schakelen, kan het Outlook-filter voor ongewenste e-mail (afhankelijk van hoe het is geconfigureerd) ook bepalen of een bericht spam is en kan het berichten verplaatsen naar het Postvak IN of de map Ongewenste e-mail op basis van eigen spam en de verzameling veilige lijsten in het postvak. Zie de sectie Over instellingen voor ongewenste [e-mail in Outlook](#about-junk-email-settings-in-outlook) in dit artikel voor meer informatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Gebruik een van de volgende procedures om te controleren of u de regel voor ongewenste e-mail in een postvak hebt in- of uitgeschakeld:

- Vervang deze door de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om de waarde van de _\<MailboxIdentity\>_ **ingeschakelde** eigenschap te controleren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell gebruiken om de safelistverzameling voor een postvak te configureren

De lijst met veilige afzenders voor een postvak bevat de lijst veilige afzenders, de lijst met veilige geadresseerden en de lijst met geblokkeerde afzenders. Standaard kunnen gebruikers de safelistverzameling configureren in hun eigen postvak in Outlook of de webversie van Outlook. Beheerders kunnen de bijbehorende parameters op de cmdlet **Set-MailboxJunkEmailConfiguration** gebruiken om de safelistverzameling in het postvak van een gebruiker te configureren. Deze parameters worden in de volgende tabel beschreven.

****

|Parameter op Set-MailboxJunkEmailConfiguration|Instelling voor de webversie van Outlook|
|---|---|
|_BlockedSendersAndDomains_|**E-mail van deze afzenders of domeinen verplaatsen naar de map Ongewenste e-mail**|
|_ContactsTrusted_|**E-mail van mijn contactpersonen vertrouwen**|
|_TrustedListsOnly_|**Alleen e-mail vertrouwen van adressen in mijn lijst met veilige afzenders en domeinen en veilige adressenlijsten**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**E-mail van deze afzenders niet verplaatsen naar de map Ongewenste e-mail**|
|

<sup>\*</sup>**Opmerkingen:**

- In Exchange Online worden domeingegevens **in** de parameter Veilige afzenders of _TrustedSendersAndDomains_ niet herkend, dus gebruik alleen e-mailadressen. In zelfstandige EOP met adreslijstsynchronisatie worden domeingegevens niet standaard gesynchroniseerd, maar u kunt synchronisatie voor domeinen inschakelen. Zie [KB3019657](https://support.microsoft.com/help/3019657)voor meer informatie.

- U kunt de lijst met veilige geadresseerden niet rechtstreeks wijzigen met behulp van de cmdlet **Set-MailboxJunkEmailConfiguration** (de parameter _TrustedRecipientsAndDomains_ werkt niet). U wijzigt de lijst met veilige afzenders en deze wijzigingen worden gesynchroniseerd met de lijst met veilige geadresseerden.

Gebruik de volgende syntaxis om de safelistverzameling voor een postvak te configureren:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Gebruik de volgende syntaxis als u meerdere waarden wilt invoeren en bestaande vermeldingen voor de parameters _BlockedSendersAndDomains_ en _TrustedSendersAndDomains_ wilt overschrijven: `"<Value1>","<Value2>"...` Als u een of meer waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande gegevens, gebruikt u de volgende syntaxis: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In dit voorbeeld worden de volgende instellingen geconfigureerd voor de lijst met veilige lijsten in het postvak van Ori Epstein:

- Voeg de waarde shopping@fabrikam.com de lijst geblokkeerde afzenders toe.

- Verwijder de waarden chris@fourthcoffee.com de lijst veilige afzenders en de lijst met veilige geadresseerden.

- Hiermee worden contactpersonen in de map Contactpersonen zo geconfigureerd dat ze worden behandeld als vertrouwde afzenders.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In dit voorbeeld wordt het domein contoso.com verwijderd uit de lijst met geblokkeerde afzenders in alle gebruikerspostvakken in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Zie [Set-MailboxJunkEmailConfiguration voor](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)gedetailleerde syntaxis- en parameterinformatie.

> [!NOTE]
>
> - Als de gebruiker het postvak nog nooit heeft geopend, wordt er mogelijk een foutbericht weergegeven wanneer u de vorige opdrachten hebt uitgevoerd. Als u deze fout bij bulkbewerkingen wilt onderdrukken, voegt u de opdracht `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** toe.
>
> - Zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak, kunt u de lijst met veilige contactpersonen nog steeds configureren en kan het Outlook-filter voor ongewenste e-mail berichten verplaatsen naar het Postvak IN of de map Ongewenste e-mail. Zie de sectie Over instellingen voor ongewenste [e-mail in Outlook](#about-junk-email-settings-in-outlook) in dit artikel voor meer informatie.
>
> - Het Outlook-filter voor ongewenste e-mail heeft aanvullende instellingen voor het verzamelen van veilige afzenders (bijvoorbeeld personen die ik e-mail automatisch toevoeg aan de lijst met **veilige afzenders).** Zie Filters voor ongewenste [e-mail gebruiken om te bepalen welke berichten u ziet.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Gebruik een van de volgende procedures om te controleren of u de safelistverzameling voor een postvak hebt geconfigureerd:

- Vervang deze door de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om _\<MailboxIdentity\>_ de eigenschapswaarden te controleren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Als de lijst met waarden te lang is, gebruikt u deze syntaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Instellingen voor ongewenste e-mail in Outlook

Gebruik Groepsbeleid als u de instellingen voor het filter voor ongewenste e-mail op de client die beschikbaar zijn in Outlook, wilt inschakelen, uitschakelen en configureren. Zie beheersjabloonbestanden [(ADMX/ADML) en het Office-aanpassingshulpmiddel voor Microsoft 365-apps voor ondernemingen, Office 2019 en Office 2016,](https://www.microsoft.com/download/details.aspx?id=49030) en informatie over het implementeren van instellingen voor ongewenste e-mail, zoals de lijst met veilige [afzenders,](https://support.microsoft.com/help/2252421)met behulp van groepsbeleid.

Wanneer het Outlook-filter voor ongewenste e-mail  is ingesteld op de standaardwaarde Geen automatisch filter **in** opties voor ongewenste e-mail voor thuisgebruik, wordt niet geprobeerd berichten als spam te classificeren, maar wordt toch de lijst met veilige afzenders (de lijst met veilige afzenders, veilige geadresseerden en de lijst met geblokkeerde afzenders) gebruikt om berichten na bezorging naar de map Ongewenste \>  \> **e-mail** te \> verplaatsen. Zie Overzicht van het filter voor ongewenste e-mail voor meer informatie over [deze instellingen.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Wanneer het Filter voor ongewenste  e-mail van Outlook is ingesteld op Laag of **Hoog,** gebruikt het Outlook-filter voor ongewenste e-mail zijn eigen SmartScreen-filtertechnologie om spam te identificeren en naar de map Ongewenste e-mail te verplaatsen. Deze spamclassificatie staat los van het spamverificatieniveau (SCL) dat wordt bepaald door EOP. In feite wordt de SCL van EOP genegeerd (tenzij EOP het bericht heeft gemarkeerd om spamfilters over te slaan) en worden eigen criteria gebruikt om te bepalen of het bericht spam is. Het is natuurlijk mogelijk dat de spam spam in EOP en Outlook hetzelfde is. Zie Het beschermingsniveau van het filter voor ongewenste [e-mail wijzigen voor meer informatie over deze instellingen.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> In november 2016 is Microsoft gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen-spamdefinities blijven bestaan, maar de effectiviteit zal na verloop van tijd waarschijnlijk slechter zijn. Zie Ondersteuning voor SmartScreen in Outlook en [Exchange ingetrokken voor meer informatie.](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)

Het Outlook-filter voor ongewenste e-mail kan dus gebruikmaken van de lijst met veilige contactpersonen van het postvak en een eigen spamclassificatie om berichten naar de map Ongewenste e-mail te verplaatsen, zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak.

Outlook en de webversie van Outlook bieden beide ondersteuning voor de safelistverzameling. De safelist-verzameling wordt opgeslagen in het Exchange Online-postvak, zodat wijzigingen in de safelistverzameling in Outlook worden weergegeven in de webversie van Outlook en omgekeerd.

## <a name="limits-for-junk-email-settings"></a>Limieten voor instellingen voor ongewenste e-mail

De lijst met veilige afzenders (de lijst met veilige afzenders, veilige geadresseerden en de lijst met geblokkeerde afzenders) die is opgeslagen in het postvak van de gebruiker, wordt ook gesynchroniseerd met EOP. Bij adreslijstsynchronisatie wordt de safelist-verzameling gesynchroniseerd met Azure AD.

- De safelistverzameling in het postvak van de gebruiker heeft een limiet van 510 kB, inclusief alle lijsten, plus extra instellingen voor het filter voor ongewenste e-mail. Als een gebruiker deze limiet overschrijdt, krijgt deze een Outlook-foutmelding die er als volgende uitziet:

  > Kan niet/niet toevoegen aan de lijsten voor ongewenste e-mail op de server. U bent groter dan de toegestane grootte op de server. Het filter voor ongewenste e-mail op de server wordt uitgeschakeld totdat de lijsten voor ongewenste e-mail zijn verkleind tot de grootte die is toegestaan door de server.

  Zie [KB2669081](https://support.microsoft.com/help/2669081)voor meer informatie over deze limiet en hoe u deze kunt wijzigen.

- De gesynchroniseerde safelistverzameling in EOP heeft de volgende synchronisatielimieten:

  - In totaal 1024 vermeldingen in de lijst veilige afzenders, de lijst met veilige geadresseerden en externe contactpersonen als E-mail van mijn contactpersonen **vertrouwen** is ingeschakeld.
  - In totaal 500 vermeldingen in de lijst geblokkeerde afzenders en de lijst met geblokkeerde domeinen.

  Wanneer de inzendingslimiet van 1024 wordt bereikt, gebeurt het volgende:

  - De lijst accepteert geen items meer in PowerShell en de webversie van Outlook, maar er wordt geen foutbericht weergegeven.

    Outlook-gebruikers kunnen meer dan 1024 vermeldingen toevoegen totdat de Outlook-limiet van 510 kB wordt bereikt. In Outlook kunnen deze aanvullende vermeldingen worden gebruikt, zolang een EOP-filter het bericht niet blokkeert voordat het in het postvak wordt bezorgd (e-mailstroomregels, anti-spoofing, enzovoort).

- Bij adreslijstsynchronisatie worden de vermeldingen in de volgende volgorde gesynchroniseerd met Azure AD:

  1. E-mailcontacten **als E-mail van mijn contactpersonen** vertrouwen is ingeschakeld.
  2. De lijst met veilige afzenders en de lijst met veilige geadresseerden worden gecombineerd, gededupliceerd en alfabetisch gesorteerd telkens wanneer er een wijziging wordt aangebracht voor de eerste 1024 items.

  De eerste 1024 items worden gebruikt en relevante informatie wordt voorzien van een stempel in de berichtkoppen.

  Vermeldingen van meer dan 1024 die niet zijn gesynchroniseerd met Azure AD, worden verwerkt in Outlook (niet in de webversie van Outlook) en er wordt geen stempel in de berichtkoppen geplaatst.

Zoals u ziet,  vermindert het inschakelen van de instelling E-mail vertrouwen van mijn contactpersonen het aantal veilige afzenders en veilige geadresseerden dat kan worden gesynchroniseerd. Als dit een probleem is, raden we u aan groepsbeleid te gebruiken om deze functie uit te schakelen:

- Bestandsnaam: outlk16.opax
- Beleidsinstelling: **E-mail van contactpersonen vertrouwen**
