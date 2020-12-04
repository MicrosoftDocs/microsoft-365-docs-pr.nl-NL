---
title: Toegestane en geblokkeerde Url's beheren in de lijst Tenant toestaan/blokkeren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over de configuratie van URL-items in de lijst Tenant toestaan/blokkeren in het beveiligings & nalevings centrum.
ms.openlocfilehash: 1aae54ffd6026a7fc131017a10f9676d96be9b69
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572635"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>URL's beheren in de lijst met toegestane/geblokkeerde tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> De functies die in dit onderwerp worden beschreven, zijn in de preview-versie en kunnen worden gewijzigd, en zijn niet beschikbaar in alle organisaties.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, kunt u niet akkoord met de EOP-filter Verdict. U kunt bijvoorbeeld een goed bericht markeren als beschadigd (een fout-positief) of een onjuist bericht mag worden toegestaan via (een onwaar negatief).

Met de lijst Tenant toestaan/blokkeren in de beveiligings & nalevings centrum kunt u de Microsoft 365-filtering handmatig vervangen door de Verdicts. De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mail stroom en wanneer de gebruiker klikt. U kunt Url's opgeven voor het toestaan of blokkeren van de lijst Tenant toestaan/blokkeren.

In dit onderwerp wordt beschreven hoe u items in de lijst met toegestane/geblokkeerde tenants van de beveiligings & of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties kunt configureren met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina met de **lijst met toegestane/geblokkeerde tenants** wilt gaan, gebruikt u <https://protection.office.com/tenantAllowBlockList> .

- In dit onderwerp vindt u een beschrijving van de beschikbare URL-waarden in de [URL-syntaxis voor de sectie lijst met toegestane/geblokkeerde tenants](#url-syntax-for-the-tenant-allowblock-list)

- De lijst Tenant toestaan/blokkeren mag maximaal 500 vermeldingen voor Url's zijn.

- Een vermelding moet binnen 15 minuten actief zijn.

- Blok vermeldingen hebben voorrang op vermeldingen voor toestaan.

- Standaard verloopt de invoer van vermeldingen in de lijst Tenant toestaan/blokkeren na 30 dagen. U kunt een datum opgeven of instellen dat deze nooit verloopt.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor beveiliging & nalevings centrum.
  - Als u waarden wilt toevoegen aan of verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .
  - Voor alleen-lezen toegang tot de lijst Tenant toegestaan/blokkeren moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het Microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in het beveiligings & nalevings centrum _en_ machtigingen voor andere functies in microsoft 365. Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **alleen weergeven voor Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Gebruik het compliance-beveiligings & voor het maken van URL-vermeldingen in de lijst Tenant toestaan/blokkeren

Zie voor meer informatie over de syntaxis voor URL-vermeldingen de [URL-syntaxis voor de sectie lijst met toegestane/geblokkeerde tenants](#url-syntax-for-the-tenant-allowblock-list) in dit onderwerp.

1. Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.

2. Zorg dat op de pagina **lijst met toegestane/geblokkeerde tenants** de optie het tabblad **url's** is geselecteerd en klik op **toevoegen** .

3. Configureer de volgende instellingen in het vervolgmenu **nieuwe Url's toevoegen** dat wordt weergegeven:

   - **Url's met jokertekens toevoegen**: Voer één URL per regel in, tot maximaal 20.

   - **Blokkeren/toestaan**: Selecteer of u de opgegeven Url's wilt **toestaan** of **blokkeren** .

   - **Verloopt nooit**: Voer een van de volgende stappen uit:

     - Controleer of de instelling is uitgeschakeld (schakelt ![ uit ](../../media/scc-toggle-off.png) ) en gebruik het vak **verloopt op** om de vervaldatum voor de items op te geven.

     of

     - Zet de wisselknop naar rechts om de items zodanig te configureren dat deze nooit verloopt: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Optionele opmerking**: Voer een beschrijvende tekst voor de vermeldingen in.

4. Wanneer u klaar bent, klikt u op **toevoegen**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>De beveiligings & voor compliance gebruiken om vermeldingen weer te geven in de lijst Tenant toestaan/blokkeren

1. Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.

2. Selecteer het tabblad **url's** .

Klik op de volgende kolomkoppen om te sorteren in oplopende of aflopende volgorde:

- **Value**
- **Actie**: **blokkeren** of **toestaan**.
- **Laatste update datum**
- **Vervaldatum**
- **Ziet**

Klik op **groeperen** om de items te groeperen op **actie** (**blokkeren** of **toestaan**) of **geen**.

Klik op **zoeken**, typ de gehele of gedeeltelijke waarde en druk op ENTER om een bepaalde waarde te zoeken. Wanneer u klaar bent, klikt u op de knop **Zoek** actie wissen ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Klik op **filter**. Configureer de volgende instellingen in de **gefilterde** flyout van het filter dat wordt weergegeven:

- **Actie**: Selecteer **toestaan**, **blokkeren** of beide.

- **Verloopt nooit**: selecteren (uitschakelen ![ ](../../media/scc-toggle-off.png) ) of aan ( ![ wisselknop ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).

- **Laatst bijgewerkt**: Selecteer een begindatum (**van**), een einddatum (**en**) of beide.

- **Vervaldatum**: Selecteer een begindatum (**van**), een einddatum (**en**) of beide.

Wanneer u klaar bent, klikt u op **toepassen**.

Als u bestaande filters wilt wissen, klikt u op **filter** en klikt u in het **filter** flyout dat wordt weergegeven op **filters wissen**.

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Met behulp van het compliance-beveiligings & voor het wijzigen van vermeldingen in de lijst Tenant toestaan/blokkeren

U kunt de URL-waarde zelf niet wijzigen. In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.

1. Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.

2. Selecteer het tabblad **url's** .

3. Selecteer de vermelding die u wilt wijzigen en klik vervolgens op het **Edit** ![ pictogram bewerken bewerken ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. Configureer de volgende instellingen in het vervolgmenu dat wordt weergegeven:

   - **Blokkeren/toestaan**: Selecteer **accepteren** of **blokkeren**.

   - **Verloopt nooit**: Voer een van de volgende stappen uit:

     - Controleer of de instelling is uitgeschakeld (uitgeschakeld ![ ](../../media/scc-toggle-off.png) ) en gebruik het vak **verloopt op** om de verloopdatum voor de invoer op te geven.

     of

     - Schuif de wisselknop naar rechts om het item zo te configureren dat het nooit verloopt: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Optionele opmerking**: Typ een beschrijvende tekst voor de vermelding.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Met behulp van het compliance-beveiligings & voor het verwijderen van vermeldingen uit de lijst Tenant toestaan/blokkeren

1. Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **bedreigings beheer** van de \> **Policy** \> **Tenant**.

2. Selecteer het tabblad **url's** .

3. Selecteer de vermelding die u **wilt verwijderen en klik op** ![ verwijderen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. In het waarschuwingsvenster dat wordt weergegeven, klikt u op **verwijderen**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken voor het configureren van de lijst met toegestane/geblokkeerde tenants

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om vermeldingen toe te voegen in de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt een URL-blok vermelding toegevoegd voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com). Aangezien we de parameters voor ExpirationDate en verstrijken niet gebruiken, verloopt de invoer na 30 dagen.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Zie [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om vermeldingen weer te geven in de lijst met toegestane/geblokkeerde tenants

Als u vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In het volgende voorbeeld worden alle geblokkeerde Url's geretourneerd.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Zie [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om vermeldingen te wijzigen in de lijst met toegestane/geblokkeerde tenants

U kunt de URL-waarde zelf niet wijzigen. In plaats daarvan moet u de vermelding verwijderen en opnieuw maken.

Gebruik de volgende syntaxis om vermeldingen te wijzigen in de lijst toestaan/blokkeren van de Tenant:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In dit voorbeeld wordt de vervaldatum van het opgegeven item gewijzigd.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Zie [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>PowerShell gebruiken om vermeldingen te verwijderen uit de lijst toestaan/blokkeren van de Tenant

Gebruik de volgende syntaxis om vermeldingen te verwijderen uit de lijst toestaan/blokkeren van de Tenant:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

In dit voorbeeld wordt de opgegeven URL-vermelding uit de lijst toestaan/blok Tenant verwijderd.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Zie [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntaxis voor de lijst met toegestane/geblokkeerde tenants

- IP4v en IPv6-adressen zijn toegestaan, maar de TCP/UDP-poorten zijn niet toegestaan.

- Bestandsextensies zijn niet toegestaan (bijvoorbeeld test.pdf).

- Unicode wordt niet ondersteund, maar punycode is.

- Hostnamen zijn toegestaan als alle volgende instructies waar zijn:

  - De hostname bevat een punt.
  - Het teken links van de periode moet minimaal één teken bevatten.
  - Rechts van de periode bestaan minimaal twee tekens.

  Dit is bijvoorbeeld `t.co` toegestaan; `.com` of `contoso.` niet toegestaan.

- Subpaden zijn niet impliciet.

  Dit is bijvoorbeeld `contoso.com` niet inbegrepen `contoso.com/a` .

- Jokertekens (*) zijn toegestaan in de volgende scenario's:

  - Een sterretje links moet worden gevolgd door een punt voor het opgeven van een subdomein.

    `*.contoso.com`Is bijvoorbeeld toegestaan; mag `*contoso.com` niet worden toegestaan.

  - Een jokerteken voor rechts moet de volgende schuine streep (/) volgen om een pad op te geven.

    Dit is bijvoorbeeld `contoso.com/*` toegestaan; `contoso.com*` of `contoso.com/ab*` niet toegestaan.

  - Alle subpaden zijn niet impliciet door een juiste jokerteken.

    Dit is bijvoorbeeld `contoso.com/*` niet inbegrepen `contoso.com/a` .

  - `*.com*` is ongeldig (geen oplosbaar domein en de juiste jokertekens volgen geen schuine streep naar rechts).

  - Jokertekens zijn niet toegestaan in IP-adressen.

- Het tilde (~) is beschikbaar in de volgende scenario's:

  - Een wegge tilde houdt een domein en alle subdomeinen in.

    Bijvoorbeeld `~contoso.com` bevat `contoso.com` en `*.contoso.com` .

- URL-vermeldingen die protocollen bevatten (bijvoorbeeld, `http://` `https://` of `ftp://` ), mislukken omdat URL-vermeldingen op alle protocollen van toepassing zijn.

- Een gebruikersnaam of wachtwoord wordt niet ondersteund of vereist.

- Aanhalingstekens (' of ') zijn ongeldige tekens.

- Een URL moet alle redirecties bevatten, waar mogelijk.

### <a name="url-entry-scenarios"></a>Scenario's voor URL-invoer

Geldige URL-vermeldingen en de bijbehorende resultaten worden beschreven in de volgende secties.

#### <a name="scenario-no-wildcards"></a>Scenario: geen jokertekens

**Invoer**: `contoso.com`

- **Overeenkomst toestaan**: contoso.com

- Mag **niet worden vergeleken**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
- **Blok treffer**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Blok niet-gerelateerde** waarde: ABC-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: links jokerteken (subdomein)

**Invoer**: `*.contoso.com`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - www.contoso.com
  - xyz.abc.contoso.com

- **Niet-gematchte** en **geblokkeerde blokkeren**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: rechts jokerteken boven aan het pad

**Invoer**: `contoso.com/a/*`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso. com/a/? q = joe@t. com

- **Niet-gematchte** en **geblokkeerde blokkeren**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
#### <a name="scenario-left-tilde"></a>Scenario: de tilde links

**Invoer**: `~contoso.com`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Niet-gematchte** en **geblokkeerde blokkeren**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: achtervoegsel van jokerteken

**Invoer**: `contoso.com/*`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - contoso. com/? q = whatever@fabrikam. com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Niet-afgestemde** en niet- **gematchte blokkeren** toestaan: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: het subdomein met jokertekens en het achtervoegsel rechts

**Invoer**: `*.contoso.com/*`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Niet-afgestemde** en niet- **gematchte blokkeren** toestaan: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: linker-en rechter tilde

**Invoer**: `~contoso.com~`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Niet-gematchte** en **geblokkeerde blokkeren**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adres

**Invoer**: `1.2.3.4`

- **Overeenkomst toestaan** en **blokkeren** toestaan: 1.2.3.4

- **Niet-gematchte** en **geblokkeerde blokkeren**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adres met jokerteken rechts

**Invoer**: `1.2.3.4/*`

- Overeenkomst toestaan en **blokkeren** **toestaan** :

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Voorbeelden van ongeldige vermeldingen

De volgende vermeldingen zijn ongeldig:

- **Ontbrekende of ongeldige domein waarden**:

  - uitgeverij
  - \*uitgeverij.\*
  - \*. com
  - \*. PDF

- **Jokertekens voor tekst of zonder spaties**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-adressen met poorten**:

  - contoso.com:443
  - abc.contoso.com:25

- **Niet-beschrijvende jokertekens**:

  - \*
  - \*.\*

- **Jokertekens** voor het midden:

  - conto \* so.com
  - rel. com

- **Dubbele jokertekens**

  - contoso.com/\*\*
  - contoso.com/\*/\*
