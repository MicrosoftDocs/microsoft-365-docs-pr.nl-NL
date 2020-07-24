---
title: Uw toegestane en geblokkeerde URL's en bestanden beheren in de lijst tenant-toestaan/blokkeren
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
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u URL- en bestandsvermeldingen configureert in de lijst Tenant Toestaan/blokkeren in het Security & Compliance Center.
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391564"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a>URL’s en bestanden beheren in de lijst met toegestane/geblokkeerde websites voor de tenant

> [!NOTE]
> De functies die in dit onderwerp worden beschreven, staan in Voorbeeld, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, u het niet eens zijn met het EOP-filteroordeel. Een goed bericht kan bijvoorbeeld als slecht worden gemarkeerd (een fout-positief) of een slecht bericht kan worden toegestaan door (een vals negatief).

De tenantlijst toestaan/blokkeren in het Security & Compliance Center biedt u een manier om de Microsoft 365-filtervonnten handmatig te overschrijven. De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt. U URL's en bestanden opgeven om toe te staan of te blokkeren in de lijst tenant-toestaan/blokkeren.

In dit onderwerp wordt beschreven hoe u vermeldingen configureert in de lijst tenant-toestaan/blokkeren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Tenant allow/block list wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .

- U geeft bestanden op met de SHA256-hashwaarde van het bestand. Voer de volgende opdracht uit in een opdrachtprompt om de SHA256-hashwaarde van een bestand in Windows te zoeken:

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptuele hash (pHash) waarden zijn niet toegestaan.

- De beschikbare URL-waarden worden later in dit onderwerp beschreven in de syntaxis van de URL voor de sectie [Tenant toestaan/blokkeren.](#url-syntax-for-the-tenant-allowblock-list)

- Met de tenantlijst toestaan/blokkeren kunnen maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestandshashes.

- Een vermelding moet binnen 15 minuten actief zijn.

- Blokvermeldingen hebben voorrang op toestaan.

- Standaard verlopen vermeldingen in de lijst tenant-toestaan/blokkeren na 30 dagen. U een datum opgeven of instellen dat deze nooit verloopt.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u waarden wilt toevoegen en verwijderen uit de lijst tenant-toestaan/blokkeren, moet u lid zijn van een van de volgende rolgroepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot de tenant-lijst voor toestaan/blokkeren, moet u lid zijn van een van de volgende rolgroepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Gebruik het Security & Compliance Center om URL-vermeldingen te maken in de lijst Tenant Allow/Block

Zie de [URL-syntaxis voor de sectie Tenant toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) lijst later in dit onderwerp voor meer informatie over de syntaxis voor URL-vermeldingen.

1. Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.

2. Controleer op de pagina **Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Toevoegen**

3. Configureer in de flyout **Voor nieuwe URL's toevoegen** die wordt weergegeven de volgende instellingen:

   - **URL's met jokertekens**toevoegen : Voer één URL per regel in, tot een maximum van 20.

   - **Blokkeren/Toestaan**: Selecteer of u de opgegeven URL's wilt **toestaan** of **blokkeren.**

   - **Nooit verlopen**: Doe een van de volgende stappen:

     - Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.

     of

     - Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.

4. Klik op Toevoegen als u klaar bent met **toevoegen.**

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Gebruik het Security & Compliance Center om bestandsvermeldingen te maken in de lijst Tenant Allow/Block

1. Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.

2. Selecteer op de pagina **Tenant toestaan/blokkeren** het tabblad **Bestanden** en klik vervolgens op **Toevoegen**.

3. Configureer in de flyout **nieuwe bestanden toevoegen** die wordt weergegeven de volgende instellingen:

   - **Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, tot een maximum van 20.

   - **Blokkeren/Toestaan**: Selecteer of u de opgegeven bestanden wilt **toestaan** of **blokkeren.**

   - **Nooit verlopen**: Doe een van de volgende stappen:

     - Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermeldingen op te geven.

     of

     - Verplaats de schakelaar naar rechts om de items te configureren om nooit te verlopen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Optionele notitie**: Voer beschrijvende tekst in voor de vermeldingen.

4. Klik op Toevoegen als u klaar bent met **toevoegen.**

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen weer te geven in de lijst Tenant Allow/Block

1. Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.

2. Selecteer het tabblad **URL's** of het tabblad **Bestanden.**

Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:

- **Waarde**: De URL of de bestandshash.
- **Actie**: **Blokkeren** of **toestaan**.
- **Laatst bijgewerkte datum**
- **Vervaldatum**
- **Opmerking**

Klik **op Groeperen** om de items te groeperen op **actie** **(Blokkeren** of **Toestaan)** of **Geen**.

Klik **op Zoeken,** voer een URL of bestandswaarde geheel of gedeeltelijk in en druk op ENTER om een specifieke waarde te vinden. Wanneer u klaar bent, klikt u op **Clear search** ![ Zoekfunctie wissen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) wissen.

Klik op **Filter**. Configureer een van de volgende instellingen in de flyout **Filter** die wordt weergegeven:

- **Actie**: Selecteer **Toestaan,** **Blokkeren** of beide.

- **Nooit verlopen**: Uitzetten ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) of aan ( ![ Schakel ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) aan).

- **Laatst bijgewerkt**: Selecteer een begindatum (**Van),** een einddatum (**Naar**) of beide.

- **Vervaldatum**: Selecteer een begindatum (**Vanaf),** een einddatum (**Tot**) of beide.

Klik op **Toepassen**als u klaar bent.

Als u bestaande filters wilt wissen, klikt u op **Filter**en klikt u in de flyout **Filter** die wordt weergegeven op **Filters wissen**.

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen in de lijst Tenant allow/block te wijzigen

U de URL of bestandswaarde zelf niet wijzigen. In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.

1. Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.

2. Selecteer het tabblad **URL's** of het tabblad **Bestanden.**

3. Selecteer het item dat u wilt wijzigen en **klik** op ![ pictogram Bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) bewerken .

4. Configureer in de flyout die wordt weergegeven de volgende instellingen:

   - **Blokkeren/toestaan**: **Selecteren Toestaan** of **blokkeren**.

   - **Nooit verlopen**: Doe een van de volgende stappen:

     - Controleer of de instelling is uitgeschakeld ( ![ ](../../media/scc-toggle-off.png) Uitschakelen) en gebruik het vak **Verlopen op** om de vervaldatum voor de vermelding op te geven.

     of

     - Verplaats de schakelaar naar rechts om de vermelding te configureren om nooit te verlopen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Optionele notitie**: Voer beschrijvende tekst in voor de vermelding.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Gebruik het Security & Compliance Center om URL- en bestandsvermeldingen uit de lijst tenant-toestaan/blokkeren te verwijderen

1. Ga in het Security & Compliance Center naar Tenant Allow/Block Lists **voor bedreigingsbeheerbeleid** \> **Policy** \> **Tenant Allow/Block Lists**.

2. Selecteer het tabblad **URL's** of het tabblad **Bestanden.**

3. Selecteer het item dat u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Klik in het waarschuwingsdialoogvenster dat wordt weergegeven op **Verwijderen**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om de tenant-lijst voor toestaan/blokkeren te configureren

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om URL- en bestandsvermeldingen toe te voegen in de lijst Tenant Toestaan/blokkeren

Als u URL- en bestandsvermeldingen wilt toevoegen in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt een URL-blokvermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com). Omdat we de parameters voor vervaldatum of niet-uitademing niet hebben gebruikt, verloopt de vermelding na 30 dagen.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

In dit voorbeeld wordt een bestand toegevoegd voor de opgegeven bestanden die nooit verlopen.

Zie [Nieuwe-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om URL- en bestandsvermeldingen weer te geven in de lijst Tenant Toestaan/blokkeren

Als u URL- en bestandsvermeldingen in de lijst Tenant toestaan/blokkeren wilt weergeven, gebruikt u de volgende syntaxis:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In dit voorbeeld worden alle geblokkeerde URL's geretourneerd.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

In dit voorbeeld worden gegevens geretourneerd voor de opgegeven bestandshashwaarde.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Zie Lijstitems voor gedetailleerde syntaxis en [parametergegevens](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om URL- en bestandsvermeldingen in de lijst tenant-toestaan/blokkeren te wijzigen

U de URL of bestandswaarde zelf niet wijzigen. In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.

Als u URL- en bestandsvermeldingen in de lijst Tenant toestaan/blokkeren wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt de vervaldatum van de opgegeven vermelding gewijzigd.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Zie [Set-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>PowerShell gebruiken om URL- en bestandsvermeldingen uit de lijst tenant-toestaan/blokkeren te verwijderen

Als u URL- en bestandsvermeldingen wilt verwijderen uit de lijst tenant-toestaan/blokkeren, gebruikt u de volgende syntaxis:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

In dit voorbeeld wordt de opgegeven URL-vermelding verwijderd uit de lijst tenant-toestaan/blokkeren.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Zie [Remove-TenantAllowBlockListIteMs voor](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)gedetailleerde syntaxis- en parametergegevens .

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntaxis voor de lijst Tenant toestaan/blokkeren

- IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.

- Bestandsnaamextensies zijn niet toegestaan (bijvoorbeeld test.pdf).

- Unicode wordt niet ondersteund, maar Punycode wel.

- Hostnamen zijn toegestaan als alle volgende instructies waar zijn:

  - De hostnaam bevat een periode.
  - Er is ten minste één teken aan de linkerkant van de periode.
  - Er zijn ten minste twee tekens aan de rechterkant van de periode.

  Is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` zijn niet toegestaan.

- Subpaden worden niet geïmpliceerd.

  Omvat bijvoorbeeld `contoso.com` niet `contoso.com/a` .

- Jokertekens (*) zijn toegestaan in de volgende scenario's:

  - Een linker wildcard moet worden gevolgd door een periode om een subdomein op te geven.

    Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.

  - Een rechter wildcard moet een slash voorwaarts (/) volgen om een pad op te geven.

    Is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` zijn niet toegestaan.

  - Alle subpaden worden niet geïmpliceerd door een juiste wildcard.

    Omvat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .

  - `*.com*`is ongeldig (geen oplosbaar domein en de juiste wildcard volgt geen slash).

  - Wildcards zijn niet toegestaan in IP-adressen.

- Het teken tilde (~) is beschikbaar in de volgende scenario's:

  - Een linker tilde impliceert een domein en alle subdomeinen.

    Bijvoorbeeld `~contoso.com` omvat `contoso.com` en `*.contoso.com` .

- URL-vermeldingen die protocollen bevatten (bijvoorbeeld `http://` `https://` , of ) `ftp://` mislukken, omdat URL-vermeldingen van toepassing zijn op alle protocollen.

- Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.

- Citaten (' of ') zijn ongeldige tekens.

- Een URL moet waar mogelijk alle omleidingen bevatten.

### <a name="url-entry-scenarios"></a>URL-invoerscenario's

Geldige URL-vermeldingen en de resultaten ervan worden beschreven in de volgende secties.

#### <a name="scenario-no-wildcards"></a>Scenario: Geen wildcards

**Vermelding**:`contoso.com`

- **Match toestaan**: contoso.com

- **Niet overeenkomen met:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
- **Blokwedstrijd**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blok niet aan elkaar gewaagd**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Linker wildcard (subdomein)

**Vermelding**:`*.contoso.com`

- Match en **Block match** **toestaan:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Niet overeenkomen en** **Blokkeren niet overeenkomen:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Juiste wildcard boven aan het pad

**Vermelding**:`contoso.com/a/*`

- Match en **Block match** **toestaan:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Niet overeenkomen en** **Blokkeren niet overeenkomen:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
#### <a name="scenario-left-tilde"></a>Scenario: Linker tilde

**Vermelding**:`~contoso.com`

- Match en **Block match** **toestaan:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Niet overeenkomen en** **Blokkeren niet overeenkomen:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Rechts wildcard achtervoegsel

**Vermelding**:`contoso.com/*`

- Match en **Block match** **toestaan:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Subdomein voor linker wildcard en het achtervoegsel van de rechter wildcard

**Vermelding**:`*.contoso.com/*`

- Match en **Block match** **toestaan:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Niet overeenkomen en** **Blok niet overeenkomen :** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Links en rechts tilde

**Vermelding**:`~contoso.com~`

- Match en **Block match** **toestaan:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Niet overeenkomen en** **Blokkeren niet overeenkomen:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adres

**Vermelding**:`1.2.3.4`

- **Wedstrijd en** **blok wedstrijd toestaan**: 1.2.3.4

- **Niet overeenkomen en** **Blokkeren niet overeenkomen:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adres met juiste wildcard

**Vermelding**:`1.2.3.4/*`

- Match en **Block match** **toestaan:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Voorbeelden van ongeldige vermeldingen

De volgende vermeldingen zijn ongeldig:

- **Ontbrekende of ongeldige domeinwaarden:**

  - Contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Wildcard op tekst of zonder spatiëringtekens:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-adressen met poorten:**

  - contoso.com:443
  - abc.contoso.com:25

- **Niet-beschrijvende wildcards**:

  - \*
  - \*.\*

- **Middelste wildcards**:

  - conto \* so.com
  - conto ~ so.com

- **Dubbele wildcards**

  - contoso.com/\*\*
  - contoso.com/\*/\*
