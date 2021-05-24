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
description: Beheerders kunnen leren hoe u de instellingen voor ongewenste e-mail configureert in Exchange Online postvakken. Veel van deze instellingen zijn beschikbaar voor gebruikers in Outlook of Outlook op internet.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a401321645530d3d66ebcccd6b8aea27ce21d6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624799"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met postvakken in Exchange Online, worden de instellingen voor organisatieantispam bepaald door Exchange Online Protection (EOP). Zie Bescherming tegen [spam in EOP voor meer informatie.](anti-spam-protection.md)

Maar er zijn ook specifieke antispaminstellingen die beheerders kunnen configureren op afzonderlijke postvakken in Exchange Online:

- **De regel ongewenste** e-mail in- of uitschakelen: de regel ongewenste e-mail is een verborgen regel voor Postvak IN met de naam Regel ongewenste e-mail die standaard is ingeschakeld in elk postvak. De regel ongewenste e-mail bepaalt de volgende functies:

  - Berichten verplaatsen naar de map Ongewenste e-mail op basis van antispambeleid: Wanneer een antispambeleid is geconfigureerd met de actie Bericht verplaatsen naar map Ongewenste e-mail voor een uitspraak over het filteren van ongewenste e-mail, wordt het bericht met de filterregel ongewenste e-mail verplaatst naar de map Ongewenste **e-mail** nadat het bericht in het postvak is bezorgd.  Zie Antispambeleid configureren in EOP voor meer informatie over het filteren van spam [in antispambeleid.](configure-your-spam-filter-policies.md) Als zap (Zero Hour Auto Purge) bepaalt dat een bezorgd bericht spam of phish is, wordt  het bericht met de filterregel ongewenste e-mail verplaatst naar de map Ongewenste e-mail voor Bericht verplaatsen naar ongewenste e-mail map spamfilteracties. Zie Auto [purge (ZAP)](zero-hour-auto-purge.md)van het uur in Exchange Online voor meer informatie over ZAP.

  - Instellingen voor ongewenste e-mail die gebruikers voor zichzelf configureren in Outlook of Outlook op het **web:** De _safelistverzameling_ is de lijst met Safe-afzenders, de lijst met Safe-geadresseerden en de lijst Geblokkeerde afzenders in elk postvak. De vermeldingen in deze lijsten bepalen of de regel ongewenste e-mail het bericht verplaatst naar het Postvak IN of de map Ongewenste e-mail. Gebruikers kunnen de safelistverzameling configureren voor hun eigen postvak in Outlook of Outlook op internet (voorheen bekend als Outlook Web App). Beheerders kunnen de safelistverzameling configureren in het postvak van elke gebruiker.

Wanneer de regel voor ongewenste e-mail is ingeschakeld in het postvak, kan EOP  berichten naar de map Ongewenste e-mail verplaatsen op basis van de actie voor het filteren van ongewenste e-mail Bericht verplaatsen naar de map Ongewenste e-mail of de lijst Geblokkeerde afzenders in het postvak en voorkomen dat berichten worden bezorgd in de map Ongewenste e-mail (op basis van de lijst met afzenders van Safe in het postvak).

 Wanneer de regel voor ongewenste e-mail is uitgeschakeld in het postvak, kan EOP  berichten niet verplaatsen naar de map Ongewenste e-mail op basis van de actie Voor spamfiltering Bericht verplaatsen naar de map Ongewenste e-mail of de safelistverzameling in het postvak.

Beheerders kunnen Exchange Online PowerShell gebruiken om de status van de regel voor ongewenste e-mail in postvakken uit te schakelen, in te schakelen en weer te geven. Beheerders kunnen Exchange Online PowerShell ook gebruiken om items in de safelistverzameling voor postvakken (de lijst Safe Afzenders, de lijst Safe Geadresseerden en de lijst Geblokkeerde afzenders) te configureren.

> [!NOTE]
> Berichten van afzenders die gebruikers hebben toegevoegd aan hun eigen Safe Lijsten met afzenders, slaan verbindingsfilters over als onderdeel van EOP (de SCL is -1). Als u wilt voorkomen dat gebruikers items toevoegen aan hun lijst met Safe-afzenders in Outlook, gebruikt u Groepsbeleid zoals vermeld in de sectie Over ongewenste e-mail [in Outlook](#about-junk-email-settings-in-outlook) sectie verder in dit artikel. Beleidsfilters, inhoudsfilters en Defender Office 365 controles worden nog steeds toegepast op de berichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U kunt alleen Exchange Online PowerShell gebruiken om de procedures in dit artikel uit te voeren. Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- Voordat u de procedures in dit artikel kunt uitvoeren, moet Exchange Online machtigingen zijn toegewezen. U hebt met name de rol E-mailontvangers nodig (die standaard is toegewezen aan de  rollengroepen Organisatiebeheer, Geadresseerdenbeheer  en  Aangepaste e-mailontvangers) of de rol Gebruikersopties (die standaard is toegewezen aan de rollengroepen Organisatiebeheer en Helpdesk).    Als u gebruikers wilt toevoegen aan rollengroepen in Exchange Online, zie [Rollengroepen wijzigen in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups) Houd er rekening mee dat gebruikers met standaardmachtigingen dezelfde procedures kunnen uitvoeren in hun eigen postvak, zolang ze toegang hebben tot [Exchange Online PowerShell.](/powershell/exchange/disable-access-to-exchange-online-powershell)

- In hybride omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de uitspraak voor EOP-spamfilters te vertalen, zodat de regel voor ongewenste e-mail het bericht naar de map Ongewenste e-mail kan verplaatsen. Zie [EOP configureren voor spam](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)in de map Ongewenste e-mail in hybride omgevingen voor meer informatie.

- Safe Afzenders voor gedeelde postvakken worden niet automatisch gesynchroniseerd met Azure AD en EOP.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Gebruik Exchange Online PowerShell om de regel voor ongewenste e-mail in of uit te schakelen in een postvak

> [!NOTE]
> U kunt de cmdlet **Set-MailboxJunkEmailConfiguration** alleen gebruiken om de regel ongewenste e-mail uit te schakelen in een postvak dat is geopend in Outlook (in de modus Exchange met cache) of Outlook op het web. Als het postvak niet is geopend, krijgt u de foutmelding: Als u deze fout wilt onderdrukken voor bulkbewerkingen, kunt u toevoegen aan de opdracht `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` Postvakvak **instellenJunkEmailConfiguration.**

Als u de regel ongewenste e-mail in een postvak wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

In dit voorbeeld wordt de regel voor ongewenste e-mail in het postvak van Ori Epstein uitgeschakeld.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

In dit voorbeeld wordt de regel voor ongewenste e-mail uitgeschakeld voor alle postvakken van gebruikers in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Zie [Set-MailboxJunkEmailConfiguration (Set-MailboxJunkEmailConfiguration)](/powershell/module/exchange/set-mailboxjunkemailconfiguration)voor gedetailleerde syntaxis- en parametergegevens.

> [!NOTE]
>
> - Als de gebruiker zijn postvak nog nooit heeft geopend, krijgt u mogelijk een foutmelding wanneer u de vorige opdracht uit te voeren. Als u deze fout wilt onderdrukken voor bulkbewerkingen, voegt u deze toe `-ErrorAction SilentlyContinue` aan de **opdracht Set-MailboxJunkEmailConfiguration.**
>
> - Zelfs als u de regel ongewenste e-mail uit schakelt, kan het Outlook filter voor ongewenste e-mail (afhankelijk van hoe het is geconfigureerd) ook bepalen of een bericht spam is en kunnen berichten worden verplaatst naar het Postvak IN of Ongewenste e-mail op basis van de eigen spam-uitspraak en de safelistverzameling in het postvak. Zie De instellingen voor ongewenste e-mail [in Outlook](#about-junk-email-settings-in-outlook) in dit artikel voor meer informatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de regel voor ongewenste e-mail in een postvak hebt ingeschakeld of uitgeschakeld, gebruikt u een van de volgende procedures:

- Vervang de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om de eigenschapswaarde _\<MailboxIdentity\>_ **Ingeschakeld te** verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Gebruik Exchange Online PowerShell om de safelistverzameling in een postvak te configureren

De safelistverzameling in een postvak bevat de lijst Safe afzenders, de lijst Safe geadresseerden en de lijst Geblokkeerde afzenders. Standaard kunnen gebruikers de safelistverzameling configureren in hun eigen postvak in Outlook of Outlook op internet. Beheerders kunnen de bijbehorende parameters op de cmdlet **Set-MailboxJunkEmailConfiguration** gebruiken om de safelistverzameling in het postvak van een gebruiker te configureren. Deze parameters worden in de volgende tabel beschreven.

****

|Parameter op Set-MailboxJunkEmailConfiguration|Outlook op het web|
|---|---|
|_BlockedSendersAndDomains_|**E-mail van deze afzenders of domeinen verplaatsen naar mijn map Ongewenste e-mail**|
|_ContactenTrusted_|**E-mail van mijn contactpersonen vertrouwen**|
|_TrustedListsOnly_|**Alleen e-mail vertrouwen van adressen in mijn Safe afzenders en domeinenlijst en Safe adressenlijsten**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**E-mail van deze afzenders niet verplaatsen naar mijn map Ongewenste e-mail**|
|

<sup>\*</sup>**Opmerkingen**:

- In Exchange Online worden **domeingegevens** in de lijst Safe afzenders of de parameter _TrustedSendersAndDomains_ niet herkend, dus alleen e-mailadressen gebruiken. In zelfstandige EOP met adreslijstsynchronisatie worden domeingegevens niet standaard gesynchroniseerd, maar kunt u synchronisatie voor domeinen inschakelen. Zie [KB3019657](https://support.microsoft.com/help/3019657)voor meer informatie.

- U kunt de lijst Safe geadresseerden niet rechtstreeks wijzigen met de cmdlet **Set-MailboxJunkEmailConfiguration** (de parameter _TrustedRecipientsAndDomains_ werkt niet). U wijzigt de Safe afzenders en deze wijzigingen worden gesynchroniseerd met de Safe geadresseerden.

Gebruik de volgende syntaxis om de safelistverzameling in een postvak te configureren:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Als u meerdere waarden wilt invoeren en bestaande vermeldingen voor de parameters _BlockedSendersAndDomains_ en _TrustedSendersAndDomains_ wilt overschrijven, gebruikt u de volgende syntaxis: `"<Value1>","<Value2>"...` . Als u een of meer waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

In dit voorbeeld worden de volgende instellingen geconfigureerd voor de safelistverzameling in het postvak van Ori Epstein:

- Voeg de waarde shopping@fabrikam.com toe aan de lijst Geblokkeerde afzenders.

- Verwijder de waarde chris@fourthcoffee.com uit de lijst Safe afzenders en de Safe geadresseerden.

- Hiermee configureert u contactpersonen in de map Contactpersonen om te worden behandeld als vertrouwde afzenders.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

In dit voorbeeld wordt het domein contoso.com verwijderd uit de lijst Geblokkeerde afzenders in alle postvakken van gebruikers in de organisatie.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Zie [Set-MailboxJunkEmailConfiguration (Set-MailboxJunkEmailConfiguration)](/powershell/module/exchange/set-mailboxjunkemailconfiguration)voor gedetailleerde syntaxis- en parametergegevens.

> [!NOTE]
>
> - Als de gebruiker zijn postvak nog nooit heeft geopend, krijgt u mogelijk een foutmelding wanneer u de vorige opdrachten uit voert. Als u deze fout wilt onderdrukken voor bulkbewerkingen, voegt u deze toe `-ErrorAction SilentlyContinue` aan de **opdracht Set-MailboxJunkEmailConfiguration.**
>
> - Zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak, kunt u de safelistverzameling nog steeds configureren en kan het filter voor ongewenste e-mail van Outlook berichten worden verplaatst naar het Postvak IN of de map Ongewenste e-mail. Zie De instellingen voor ongewenste e-mail [in Outlook](#about-junk-email-settings-in-outlook) in dit artikel voor meer informatie.
>
> - Het Outlook filter voor ongewenste e-mail heeft extra instellingen voor de safelistverzameling (bijvoorbeeld: Personen die ik e-mail stuur automatisch toevoegen aan de lijst met **Safe afzenders).** Zie Filters voor ongewenste e-mail gebruiken om [te bepalen welke berichten u ziet voor meer informatie.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u de safelistverzameling in een postvak hebt geconfigureerd, gebruikt u een van de volgende procedures:

- Vervang de naam, alias of het e-mailadres van het postvak en voer de volgende opdracht uit om _\<MailboxIdentity\>_ de eigenschapswaarden te verifiëren:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Als de lijst met waarden te lang is, gebruikt u deze syntaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Instellingen voor ongewenste e-mail in Outlook

Als u de instellingen voor het filter voor ongewenste e-mail aan de clientzijde wilt inschakelen, uitschakelen en configureren die beschikbaar zijn in Outlook, gebruikt u Groepsbeleid. Zie Beheerssjabloonbestanden [(ADMX/ADML) en het aanpassingshulpmiddel Office voor Microsoft 365-apps voor ondernemingen, Office 2019 en Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) en Instellingen voor ongewenste e-mail implementeren, zoals de [lijst met Safe-afzenders,](https://support.microsoft.com/help/2252421)met groepsbeleid voor meer informatie.

Wanneer het filter voor ongewenste e-mail van Outlook  is ingesteld op de standaardwaarde Geen automatische filtering **in** Opties voor ongewenste e-mail voor thuisgebruik , probeert Outlook geen spam te classificeren, maar gebruikt wel de \>  \> safelistverzameling (de lijst met afzenders van Safe, Safe adressenlijst en lijst met geblokkeerde afzenders) om berichten na de bezorging naar de map Ongewenste **e-mail** te \> verplaatsen. Zie Overzicht van het filter voor ongewenste e-mail voor meer informatie over deze [instellingen.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Wanneer het Outlook filter voor ongewenste  e-mail is ingesteld op Laag of **Hoog,** gebruikt het filter voor ongewenste e-mail van Outlook zijn eigen SmartScreen-filtertechnologie om spam te identificeren en naar de map Ongewenste e-mail te verplaatsen. Deze spamclassificatie staat los van het betrouwbaarheidsniveau voor spam (SCL) dat wordt bepaald door EOP. In feite wordt Outlook SCL van EOP genegeerd (tenzij EOP het bericht heeft gemarkeerd om spamfilters over te slaan) en worden eigen criteria gebruikt om te bepalen of het bericht spam is. Het is natuurlijk mogelijk dat de spam-uitspraak van EOP en Outlook hetzelfde zijn. Zie Het beveiligingsniveau wijzigen in het filter ongewenste [e-mail](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)voor meer informatie over deze instellingen.

> [!NOTE]
> In november 2016 is Microsoft gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen-spamdefinities zijn op hun plaats gebleven, maar de effectiviteit ervan zal waarschijnlijk na verloop van tijd verslechteren. Zie Ondersteuning voor [SmartScreen in Outlook en](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)Exchange voor meer informatie.

Het Outlook filter voor ongewenste e-mail kan dus de safelistverzameling van het postvak en de eigen spamclassificatie gebruiken om berichten naar de map Ongewenste e-mail te verplaatsen, zelfs als de regel voor ongewenste e-mail is uitgeschakeld in het postvak.

Outlook en Outlook op internet ondersteunen beide de safelist-verzameling. De safelistverzameling wordt opgeslagen in het Exchange Online postvak, dus wijzigingen in de safelistverzameling in Outlook worden weergegeven in Outlook op internet en omgekeerd.

## <a name="limits-for-junk-email-settings"></a>Limieten voor instellingen voor ongewenste e-mail

De safelistverzameling (de lijst Safe afzenders, Safe adressenlijst en lijst met geblokkeerde afzenders) die is opgeslagen in het postvak van de gebruiker, wordt ook gesynchroniseerd met EOP. Met adreslijstsynchronisatie wordt de safelist-verzameling gesynchroniseerd met Azure AD.

- De safelistverzameling in het postvak van de gebruiker heeft een limiet van 510 KB, inclusief alle lijsten, plus extra instellingen voor het filter voor ongewenste e-mail. Als een gebruiker deze limiet overschrijdt, krijgt deze een foutmelding Outlook ziet er als volgende uit:

  > Kan/kan niet toevoegen aan de lijsten met ongewenste e-mail van de server. U bent groter dan de toegestane grootte op de server. Het filter Ongewenste e-mail op de server wordt uitgeschakeld totdat uw lijsten met ongewenste e-mail zijn verkleind tot de grootte die is toegestaan door de server.

  Zie [KB2669081](https://support.microsoft.com/help/2669081)voor meer informatie over deze limiet en hoe u deze kunt wijzigen.

- De gesynchroniseerde safelistverzameling in EOP heeft de volgende synchronisatielimieten:

  - In totaal 1024 vermeldingen in de lijst Safe afzenders, de lijst Safe geadresseerden en externe contactpersonen als E-mail van mijn contactpersonen vertrouwen **is** ingeschakeld.
  - In totaal 500 vermeldingen in de lijst Geblokkeerde afzenders en geblokkeerde domeinen.

  Wanneer de limiet voor 1024-invoer is bereikt, gebeuren de volgende dingen:

  - De lijst accepteert geen vermeldingen meer in PowerShell en Outlook op internet, maar er wordt geen fout weergegeven.

    Outlook gebruikers kunnen meer dan 1024 items toevoegen totdat ze de limiet van 510 KB Outlook bereiken. Outlook kunnen deze aanvullende vermeldingen gebruiken, zolang een EOP-filter het bericht niet blokkeert vóór de bezorging in het postvak (regels voor e-mailstroom, anti-spoofing, enzovoort).

- Bij adreslijstsynchronisatie worden de vermeldingen in de volgende volgorde gesynchroniseerd met Azure AD:

  1. E-mailcontacten **als e-mail van mijn contactpersonen** vertrouwen is ingeschakeld.
  2. De Safe lijst met afzenders en Safe adressenlijst worden gecombineerd, gededupliceerd en alfabetisch gesorteerd wanneer er een wijziging wordt aangebracht voor de eerste 1024 vermeldingen.

  De eerste 1024 vermeldingen worden gebruikt en relevante informatie wordt gestempeld in de berichtkoppen.

  Items in meer dan 1024 die niet zijn gesynchroniseerd met Azure AD, worden verwerkt door Outlook (niet Outlook op het web) en er worden geen gegevens in de berichtkoppen gestempeld.

Zoals u kunt zien, vermindert het inschakelen van de instelling E-mail vertrouwen van mijn contactpersonen het aantal Safe afzenders en Safe geadresseerden dat kan worden gesynchroniseerd.  Als dit een probleem is, raden we u aan groepsbeleid te gebruiken om deze functie uit te schakelen:

- Bestandsnaam: outlk16.opax
- Beleidsinstelling: **E-mail van contactpersonen vertrouwen**