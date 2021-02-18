---
title: Uw sta- en blokkeringen beheren in de tenantlijst toestaan/blokkeren
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
description: Beheerders kunnen in de beveiligingsportal meer informatie krijgen over het configureren van toegestane en geblokkeerde tenants in de lijst Met toegestane/geblokkeerde tenants.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290163"
---
# <a name="manage-the-tenant-allowblock-list"></a>Tenant Toestaan/Blokkeren-lijst beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> De functies die in dit artikel worden beschreven, zijn in preview beschikbaar, kunnen worden gewijzigd en zijn niet in alle organisaties beschikbaar.
>
> U kunt momenteel geen **toegestane** items configureren in de tenantlijst Toestaan/Blokkeren.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, bent u het mogelijk niet eens met de filtering van EOP. Een goed bericht kan bijvoorbeeld als slecht zijn gemarkeerd (een fout-positief) of een slecht bericht kan zijn toegestaan (een fout-negatief).

Met de lijst met tenants toestaan/blokkeren in het & compliancecentrum kunt u het filterbeleid van Microsoft 365 handmatig overschrijven. De tenantlijst toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en tijdens het klikken door de gebruiker. U kunt URL's of bestanden opgeven die u altijd wilt blokkeren.

In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Tenant toestaan/blokkeren wilt** gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .

- U geeft bestanden op met de hashwaarde SHA256 van het bestand. U kunt de SHA256-hashwaarde van een bestand in Windows vinden door de volgende opdracht uit te voeren in een opdrachtprompt:

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Een voorbeeldwaarde is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptual hash (pHash) waarden worden niet ondersteund.

- De beschikbare URL-waarden worden beschreven in de [URL-syntaxis voor de sectie Toestaan/blokkeerlijst](#url-syntax-for-the-tenant-allowblock-list) voor tenants verderop in dit artikel.

- De tenantlijst toestaan/blokkeren biedt maximaal 500 vermeldingen voor URL's en 500 vermeldingen voor bestand-hashes.

- Een item moet binnen 15 minuten actief zijn.

- Standaard verlopen vermeldingen in de lijst met toegestane/geblokkeerde tenants na 30 dagen. U kunt een datum opgeven of instellen dat deze nooit verloopt.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u waarden wilt toevoegen aan en verwijderen uit de tenantlijst toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot de tenantlijst Toestaan/Blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Gebruik het beveiligings- & compliancecentrum om URL-vermeldingen te maken in de lijst Met toegestane/geblokkeerde tenants

Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis voor URL-vermeldingen.

1. Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**

2. Controleer op **de pagina Tenant toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op **Blokkeren**

3. Configureer **de volgende** instellingen in de flyout Blok-URL's die wordt weergegeven:

   - **Url's toevoegen die u wilt blokkeren:** voer één URL per regel in, maximaal 20.

   - **Verloopt nooit:** ga op een van de volgende stappen te werk:

     - Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de items ![ ](../../media/scc-toggle-off.png) op te geven. 

     of

     - Verplaats de schakelknop naar rechts om de vermeldingen zo te configureren dat ze nooit verlopen: ![Inschakelen](../../media/scc-toggle-on.png).

   - **Optionele opmerking:** voer beschrijvende tekst in voor de vermeldingen.

4. Klik op Toevoegen wanneer u **klaar bent.**

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Gebruik het beveiligings- & compliancecentrum om bestandsgegevens te maken in de lijst Met toegestane/geblokkeerde tenants

1. Ga in het & compliancecentrum  naar de tenant voor het \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**

2. Selecteer op **de pagina Lijst met tenants toestaan/blokkeren** het tabblad Bestanden en klik op **Blokkeren.** 

3. Configureer **de volgende instellingen in het dialoogvenster** Bestanden toevoegen om flyout te blokkeren die wordt weergegeven:

   - **Bestandshashes toevoegen:** voer één SHA256-hashwaarde per regel in, tot maximaal 20.

   - **Verloopt nooit:** ga op een van de volgende stappen te werk:

     - Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de items ![ ](../../media/scc-toggle-off.png) op te geven. 

     of

     - Verplaats de schakelknop naar rechts om de vermeldingen zo te configureren dat ze nooit verlopen: ![Inschakelen](../../media/scc-toggle-on.png).

   - **Optionele opmerking:** voer beschrijvende tekst in voor de vermeldingen.

4. Klik op Toevoegen wanneer u **klaar bent.**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Het beveiligings- & compliancecentrum gebruiken om vermeldingen weer te geven in de lijst Met toegestane/geblokkeerde tenants

1. Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**

2. Selecteer het **tabblad URL's** of het **tabblad** Bestanden.

Klik op de volgende kolomkoppen om in oplopende of aflopende volgorde te sorteren:

- **Waarde:** de URL of de bestandshash.
- **Laatst bijgewerkte datum**
- **Vervaldatum**
- **Opmerking**

Klik **op** Zoeken, voer een waarde in (een deel ervan) en druk op Enter om een specifieke waarde te zoeken. Wanneer u klaar bent, klikt u **op het pictogram Zoeken** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) verwijderen.

Klik **op Filteren.** Configureer **een van** de volgende instellingen in de flyout Filter die wordt weergegeven:

- **Nooit verlopen:** uit- of ![ ](../../media/scc-toggle-off.png) uitschakelen: ![ In-/uitschakelen: In-/uitschakelen. ](../../media/scc-toggle-on.png)

- **Laatst bijgewerkt:** selecteer een begindatum **(van),** een einddatum **(aan)** of beide.

- **Vervaldatum:** selecteer een begindatum **(van),** een einddatum **(aan)** of beide.

Klik op Toepassen wanneer u **klaar bent.**

Als u bestaande filters wilt wissen, klikt u op **Filter** en klikt u in de **flyout** Filter die wordt weergegeven op **Filters wissen.**

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Gebruik het beveiligings- & blokkeringsgegevens in de lijst met tenants toestaan/blokkeren te wijzigen

U kunt de bestaande geblokkeerde URL of bestandswaarden in een vermelding niet wijzigen. Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.

1. Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**

2. Selecteer het **tabblad URL's** of het **tabblad** Bestanden.

3. Selecteer het blok dat u wilt wijzigen en klik op **het pictogram** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Bewerken.

4. Configureer de volgende instellingen in de flyout die wordt weergegeven:

   - **Verloopt nooit:** ga op een van de volgende stappen te werk:

     - Controleer of de instelling is uitgeschakeld (in-/uitschakelen) en gebruik het vak Verloopt in om de vervaldatum voor de vermelding ![ ](../../media/scc-toggle-off.png) op te geven. 

     of

     - Verplaats de schakelknop naar rechts om de vermelding zo te configureren dat deze nooit verloopt: ![Inschakelen](../../media/scc-toggle-on.png).

   - **Optionele opmerking:** voer beschrijvende tekst voor de invoer in.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Het beveiligings- & compliancecentrum gebruiken om geblokkeerde items uit de lijst Met toegestane/geblokkeerde tenants te verwijderen

1. Ga in het & compliancecentrum  naar de tenant Voor \>  \> **risicobeheerbeleid : toegestane/geblokkeerde lijsten.**

2. Selecteer het **tabblad URL's** of het **tabblad** Bestanden.

3. Selecteer het blok dat u wilt verwijderen en klik op **het pictogram** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Verwijderen.

4. Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Exchange Online PowerShell of een zelfstandige EOP PowerShell gebruiken om de lijst met tenants toestaan/blokkeren te configureren

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>PowerShell gebruiken om geblokkeerde items toe te voegen aan de lijst Met toegestane/geblokkeerde tenants

Gebruik de volgende syntaxis om geblokkeerde items toe te voegen aan de tenantlijst Toestaan/Blokkeren:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt een BLOK-URL-vermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com). Omdat we de parameters ExpirationDate of NoExpiration niet hebben gebruikt, verloopt de invoer na 30 dagen.

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

In dit voorbeeld wordt een blokkeringsbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Zie [New-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om vermeldingen in de lijst Toestaan/blokkeren van tenants weer te geven

Gebruik de volgende syntaxis om vermeldingen weer te geven in de lijst Met toegestane/geblokkeerde tenants:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In dit voorbeeld worden alle geblokkeerde URL's als retourneert.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

In dit voorbeeld worden gegevens voor de opgegeven hash-waarde voor het bestand als resultaat gegeven.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Zie [Get-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om geblokkeerde items in de lijst Met tenant toestaan/blokkeren te wijzigen

U kunt de bestaande URL- of bestandswaarden in een blokinvoer niet wijzigen. Als u deze waarden wilt wijzigen, moet u de vermelding verwijderen en opnieuw maken.

Gebruik de volgende syntaxis om geblokkeerde items in de tenantlijst toestaan/blokkeren te wijzigen:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt de vervaldatum van de opgegeven blokkeringsdatum gewijzigd.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Zie [Set-TenantAllowBlockListItems voor](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>PowerShell gebruiken om geblokkeerde items uit de lijst Met toegestane/geblokkeerde tenants te verwijderen

Gebruik de volgende syntaxis om geblokkeerde items uit de lijst Met tenant toestaan/blokkeren te verwijderen:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

In dit voorbeeld wordt het opgegeven blok url-item verwijderd uit de lijst Met toegestane/geblokkeerde tenants.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Zie [Remove-TenantAllowBlockListItems voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)syntaxis- en parameterinformatie.

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Url-syntaxis voor de lijst met tenants toestaan/blokkeren

- IP4v- en IPv6-adressen zijn toegestaan, maar TCP/UDP-poorten niet.

- Bestandsextensies zijn niet toegestaan (bijvoorbeeld test.pdf).

- Unicode wordt niet ondersteund, maar Punycode wel.

- Hostnamen zijn toegestaan als alle volgende instructies waar zijn:
  - De hostnaam bevat een punt.
  - Er staat ten minste één teken links van de punt.
  - Er staan ten minste twee tekens rechts van de punt.

  Is bijvoorbeeld `t.co` toegestaan of `.com` niet `contoso.` toegestaan.

- Subpaths worden niet geïmpliceerd.

  Bevat bijvoorbeeld `contoso.com` niet `contoso.com/a` .

- Jokertekens (*) zijn toegestaan in de volgende scenario's:

  - Een linker-jokerteken moet worden gevolgd door een punt om een subdomein op te geven.

    Is bijvoorbeeld `*.contoso.com` toegestaan; `*contoso.com` is niet toegestaan.

  - Een rechter-jokerteken moet een slash (/) volgen om een pad op te geven.

    Is bijvoorbeeld `contoso.com/*` toegestaan of `contoso.com*` niet `contoso.com/ab*` toegestaan.

  - Alle subpathen worden niet geïmpliceerd door een rechter jokerteken.

    Bevat bijvoorbeeld `contoso.com/*` niet `contoso.com/a` .

  - `*.com*` ongeldig is (geen omsloten domein en het rechter jokerteken volgt geen slash).

  - Jokertekens zijn niet toegestaan in IP-adressen.

- Het tildeteken (~) is beschikbaar in de volgende scenario's:

  - Een linker tilde betekent een domein en alle subdomeinen.

    Bijvoorbeeld inclusief `~contoso.com` `contoso.com` en `*.contoso.com` .

- URL-vermeldingen die protocollen bevatten (bijvoorbeeld , of ) mislukken, omdat URL-vermeldingen van toepassing zijn `http://` `https://` op alle `ftp://` protocollen.

- Een gebruikersnaam of wachtwoord wordt niet ondersteund of is niet vereist.

- Aanhalingstekens (' of ") zijn ongeldige tekens.

- Een URL moet waar mogelijk alle omleidingen bevatten.

### <a name="url-entry-scenarios"></a>Scenario's voor URL-invoer

Geldige URL-vermeldingen en de resultaten worden in de volgende secties beschreven.

#### <a name="scenario-no-wildcards"></a>Scenario: Geen jokertekens

**Invoer:**`contoso.com`

- **Overeenkomst toestaan**: contoso.com

- **Geen overeenkomst toestaan:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Overeenkomst blokkeren:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blok komt niet overeen:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Linker-jokerteken (subdomein)

**Invoer:**`*.contoso.com`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Rechts-jokerteken boven aan pad

**Invoer:**`contoso.com/a/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: Linker tilde

**Invoer:**`~contoso.com`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Rechts jokertekenachtervoegsel

**Invoer:**`contoso.com/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Geen overeenkomst toestaan en** **Blokkeren niet overeen:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Linker-jokertekensubdomein en rechterachtervoegsel met jokertekens

**Invoer:**`*.contoso.com/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Geen overeenkomst toestaan en** **Blokkeren niet overeen:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Tilde links en rechts

**Invoer:**`~contoso.com~`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adres

**Invoer:**`1.2.3.4`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:** 1.2.3.4

- **Geen overeenkomst van overeenkomst toestaan** en Blokkeren niet **overeen:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adres met rechter jokerteken

**Invoer:**`1.2.3.4/*`

- **Overeenkomst en** **overeenkomst blokkeren toestaan:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Voorbeelden van ongeldige vermeldingen

De volgende vermeldingen zijn ongeldig:

- **Ontbrekende of ongeldige domeinwaarden:**

  - contoso
  - \*.contoso.\*
  - \*.COM
  - \*.PDF

- **Jokertekens in tekst of zonder spatiëringstekens:**

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
