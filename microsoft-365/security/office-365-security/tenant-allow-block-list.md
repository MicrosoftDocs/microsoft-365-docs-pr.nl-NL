---
title: Uw toegestane en geblokkeerde blokken beheren in de lijst Toestaan/blokkeren van tenant
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het configureren van toestaan en blokkeren in de lijst Tenant toestaan/blokkeren in de beveiligingsportal.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587585"
---
# <a name="manage-the-tenant-allowblock-list"></a>Tenant Toestaan/Blokkeren-lijst beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> U kunt op dit **moment geen toegestane** items configureren in de lijst Tenant toestaan/blokkeren.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, bent u het mogelijk niet eens met de uitspraak over EOP-filtering. Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).

Met de tenantlijst Toestaan/blokkeren in het Beveiligings- & Compliancecentrum kunt u handmatig de filterinspraken van Microsoft 365 overschrijven. De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt. U kunt URL's of bestanden opgeven die u altijd wilt blokkeren.

In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .

- U geeft bestanden op met de hashwaarde SHA256 van het bestand. Als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, voer u de volgende opdracht uit in een opdrachtprompt:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptuele hashwaarden (pHash) worden niet ondersteund.

- De beschikbare URL-waarden worden beschreven in de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel.

- De lijst Tenant toestaan/blokkeren staat maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes toe.

- Het maximum aantal tekens voor elke vermelding is:
  - Bestandshashes = 64
  - URL = 250

- Een item moet binnen 30 minuten actief zijn.

- Standaard verlopen vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen. U kunt een datum opgeven of instellen dat deze nooit verloopt.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  > [!NOTE]
  > 
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Gebruik het beveiligings- & compliancecentrum om URL-vermeldingen te maken in de lijst Tenant toestaan/blokkeren

Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.

1. Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**

2. Controleer op de pagina Lijst met **tenants toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**

3. Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:

   - **URL's toevoegen om te blokkeren:** Voer één URL per regel in, maximaal 20.

   - **Nooit verlopen:** Ga op een van de volgende stappen te werk:

     - Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. 

       of

     - Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen: ![Inschakelen](../../media/scc-toggle-on.png).

   - **Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.

4. Wanneer u klaar bent, klikt u op **Toevoegen.**

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Gebruik het beveiligings- & compliancecentrum om bestandsgegevens te maken in de lijst Tenant toestaan/blokkeren

1. Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**

2. Selecteer op de pagina Lijst met **tenants toestaan/blokkeren** de optie **Tabblad** Bestanden en klik vervolgens op **Blokkeren.**

3. Configureer **de volgende instellingen in het flyout** add files to block flyout that appears:

   - **Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.

   - **Nooit verlopen:** Ga op een van de volgende stappen te werk:

     - Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verloopt aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. 

     of

     - Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen: ![Inschakelen](../../media/scc-toggle-on.png).

   - **Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.

4. Wanneer u klaar bent, klikt u op **Toevoegen.**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Het beveiligings- & compliancecentrum gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven

1. Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**

2. Selecteer het **tabblad URL's** of het **tabblad** Bestanden.

Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:

- **Waarde:** De URL of de bestandshash.
- **Laatst bijgewerkte datum**
- **Vervaldatum**
- **Opmerking**

Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken. Wanneer u klaar bent, klikt u op **Zoek verwijderen Zoekpictogram** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.

Klik **op Filteren.** Configureer **een van** de volgende instellingen in het flyout Filter dat wordt weergegeven:

- **Nooit verlopen:** Uit- of ![ ](../../media/scc-toggle-off.png) uitschakelen: ![ In- of uitschakelen: In- of ](../../media/scc-toggle-on.png) uitschakelen.

- **Laatst bijgewerkt:** Selecteer een begindatum **(Van),** een einddatum **(Aan)** of beide.

- **Vervaldatum:** Selecteer een begindatum (**Van**), een einddatum (**Aan**) of beide.

Wanneer u klaar bent, klikt u op **Toepassen.**

Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Gebruik het beveiligings- & compliancecentrum om blokinzendingen in de lijst Tenant toestaan/blokkeren te wijzigen

U kunt de bestaande geblokkeerde URL of bestandswaarden in een item niet wijzigen. Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.

1. Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**

2. Selecteer het **tabblad URL's** of het **tabblad** Bestanden.

3. Selecteer de blokinvoer die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken.

4. Configureer de volgende instellingen in het flyout dat wordt weergegeven:

   - **Nooit verlopen:** Ga op een van de volgende stappen te werk:

     - Controleer of de instelling is uitgeschakeld (schakelknop uit) en gebruik het vak Verloopt op om de vervaldatum voor ![ de vermelding op te ](../../media/scc-toggle-off.png) geven. 

       of

     - Verplaats de schakelknop naar rechts om de vermelding zo te configureren dat deze nooit verloopt: ![Inschakelen](../../media/scc-toggle-on.png).

   - **Optionele opmerking:** Voer beschrijvende tekst in voor de vermelding.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Het beveiligings- & compliancecentrum gebruiken om blokinzendingen uit de lijst Met tenant toestaan/blokkeren te verwijderen

1. Ga in het & Compliance center naar Lijst met **bedreigingsbeheerbeleids** \>  \> **tenants toestaan/blokkeren.**

2. Selecteer het **tabblad URL's** of het **tabblad** Bestanden.

3. Selecteer de blokinvoer die u wilt verwijderen en klik vervolgens op **Pictogram** ![ Verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) verwijderen.

4. Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenantlijst toestaan/blokkeren te configureren

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>PowerShell gebruiken om blokgegevens toe te voegen aan de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om blokgegevens toe te voegen in de lijst Tenant Allow/Block:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com). Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om items in de lijst Tenant toestaan/blokkeren weer te geven

Gebruik de volgende syntaxis om vermeldingen in de lijst Tenant toestaan/blokkeren weer te geven:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In dit voorbeeld worden alle geblokkeerde URL's als retourneert.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om blokgegevens in de lijst Tenant toestaan/blokkeren te wijzigen

U kunt de bestaande URL- of bestandswaarden in een blokinvoer niet wijzigen. Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.

Gebruik de volgende syntaxis om blokgegevens in de lijst Tenant toestaan/blokkeren te wijzigen:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt de vervaldatum van de opgegeven blokinvoer gewijzigd.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>PowerShell gebruiken om blokgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren

Als u blokinzendingen wilt verwijderen uit de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntaxis voor de lijst Toestaan/blokkeren van tenant

- IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.

- Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).

- Unicode wordt niet ondersteund, maar Punycode wel.

- Hostnamen zijn toegestaan als alle volgende instructies waar zijn:
  - De hostnaam bevat een punt.
  - Er is ten minste één teken links van de periode.
  - Er zijn ten minste twee tekens rechts van de periode.

  Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.

- Subpathen worden niet geïmpliceerd.

  Bevat bijvoorbeeld `contoso.com` geen `contoso.com/a` .

- Jokertekens (*) zijn toegestaan in de volgende scenario's:

  - Een linker jokerteken moet worden gevolgd door een punt om een subdomein op te geven.

    Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.

  - Een jokerteken rechts moet een slash (/) volgen om een pad op te geven.

    Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.

  - Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.

    Bevat bijvoorbeeld `contoso.com/*` geen `contoso.com/a` .

  - `*.com*` ongeldig is (geen op te lossen domein en het jokerteken rechts volgt geen slash voor vooruit).

  - Jokertekens zijn niet toegestaan in IP-adressen.

- Het tildeteken (~) is beschikbaar in de volgende scenario's:

  - Een linker tilde houdt een domein en alle subdomeinen in.

    Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .

- URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.

- Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.

- Aanhalingstekens (' of ") zijn ongeldige tekens.

- Een URL moet waar mogelijk alle omleidingen bevatten.

### <a name="url-entry-scenarios"></a>Scenario's voor URL-invoer

Geldige URL-vermeldingen en de resultaten worden beschreven in de volgende secties.

#### <a name="scenario-no-wildcards"></a>Scenario: Geen jokertekens

**Vermelding**: `contoso.com`

- **Overeenkomst toestaan**: contoso.com

- **Niet-overeenkomende toestaan:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blok overeenkomst**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blok niet overeenkomend**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Jokerteken links (subdomein)

**Vermelding**: `*.contoso.com`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Jokerteken rechts boven aan pad

**Vermelding**: `contoso.com/a/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: Tilde links

**Vermelding**: `~contoso.com`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Het achtervoegsel van het jokerteken rechts

**Vermelding**: `contoso.com/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Linker jokertekensubdomein en rechterachtervoegsel jokerteken

**Vermelding**: `*.contoso.com/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Niet-overeenkomende en** **niet-overeenkomende** blokkering toestaan : contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Tilde links en rechts

**Vermelding**: `~contoso.com~`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adres

**Vermelding**: `1.2.3.4`

- **Overeenkomst toestaan** **en overeenkomst blokkeren**: 1.2.3.4

- **Niet-overeenkomende en** **niet-overeenkomende blokkering toestaan:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adres met jokerteken rechts

**Vermelding**: `1.2.3.4/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Voorbeelden van ongeldige vermeldingen

De volgende vermeldingen zijn ongeldig:

- **Ontbrekende of ongeldige domeinwaarden:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Jokerteken op tekst of zonder spatiëringstekens:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-adressen met poorten:**

  - contoso.com:443
  - abc.contoso.com:25

- **Niet-beschrijvende jokertekens:**

  - \*
  - \*.\*

- **Middelste jokertekens:**

  - conto \* so.com
  - conto~so.com

- **Dubbele jokertekens**

  - contoso.com/\*\*
  - contoso.com/\*/\*
