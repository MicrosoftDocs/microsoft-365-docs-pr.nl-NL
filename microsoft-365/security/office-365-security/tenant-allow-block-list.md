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
ms.openlocfilehash: 67c3badb86f1cfb9bf644cc202ed67e3163a6772
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933153"
---
# <a name="manage-the-tenant-allowblock-list"></a>Tenant Toestaan/Blokkeren-lijst beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.  Als uw organisatie niet beschikt over de spooffuncties zoals beschreven in dit artikel, bekijkt u de oudere spoofbeheerervaring bij Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof [intelligence in EOP.](walkthrough-spoof-intelligence-insight.md)
>
> U kunt op dit **moment geen** toegestane URL- of bestandsitems configureren in de lijst Tenant toestaan/blokkeren.

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, kunt u het niet eens zijn met de uitspraak over EOP-filtering. Een goed bericht kan bijvoorbeeld worden gemarkeerd als slecht (een onwaar positief) of een slecht bericht kan worden toegestaan (een onwaar negatief).

Met de Tenant Allow/Block List in Microsoft 365 Defender-portal kunt u handmatig de Microsoft 365 filteren. De lijst Tenant toestaan/blokkeren wordt gebruikt tijdens de e-mailstroom en op het moment dat de gebruiker klikt. U kunt de volgende typen overschrijven opgeven:

- URL's die u wilt blokkeren.
- Bestanden die u wilt blokkeren.
- Vervalste afzenders om dit toe te staan of te blokkeren. Als u de uitspraak toestaan of blokkeren overschrijven in het inzicht van spoof [intelligence,](learn-about-spoof-intelligence.md)wordt de vervalste afzender een handmatige invoer toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Spoof** in de lijst Toestaan/blokkeren van tenants. U kunt hier ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren voordat ze worden gedetecteerd door spoofinformatie.

In dit artikel wordt beschreven hoe u vermeldingen configureert in de lijst Tenant toestaan/blokkeren in de portal van Microsoft 365 Defender of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>. Als u rechtstreeks naar de **pagina Lijst met tenants toestaan/blokkeren** wilt gaan, gebruikt <https://security.microsoft.com/tenantAllowBlockList> u .

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

- U moet over toegewezen machtigingen beschikken in Exchange Online voordat u de procedures in dit artikel kunt uitvoeren:
  - **URL's en bestanden:**
    - Als u waarden wilt toevoegen en verwijderen uit de lijst Tenant toestaan/blokkeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
    - Voor alleen-lezen toegang tot de tenantlijst toestaan/blokkeren moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**
  - **Spoofing:** Een van de volgende combinaties:
    - **Organisatiebeheer**
    - **Beveiligingsbeheerder** <u>en</u> **Alleen-weergeven-configuratie** of **Alleen-weergeven organisatiebeheer**.

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Gebruik de Microsoft 365 Defender-portal om url-items te maken in de lijst Tenant Allow/Block

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** regels \> **Bedreigingsbeleidsregels** sectie \>  Tenant \> **Allow/Block Lists**.

2. Controleer op de pagina Lijst met tenants **toestaan/blokkeren** of het tabblad **URL's** is geselecteerd en klik vervolgens op ![ Pictogram blokkeren ](../../media/m365-cc-sc-create-icon.png) **blokkeren.**

3. Configureer **de volgende** instellingen in het flyout URL's blokkeren dat wordt weergegeven:
   - **URL's met jokertekens toevoegen:** Voer één URL per regel in, maximaal 20. Zie de syntaxis van de URL voor de sectie Lijst met tenants [toestaan/blokkeren](#url-syntax-for-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van URL-vermeldingen.
   - **Nooit verlopen:** Ga op een van de volgende stappen te werk:
     - Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verwijderen aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. 

       of

     - Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen: ![Inschakelen](../../media/scc-toggle-on.png).
   - **Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.

4. Wanneer u klaar bent, klikt u op **Toevoegen.**

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Gebruik de Microsoft 365 Defender-portal om blokbestandsgegevens te maken in de lijst Tenant Allow/Block

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** regels \> **Bedreigingsbeleidsregels** sectie \>  Tenant \> **Allow/Block Lists**.

2. Selecteer op de pagina Lijst met  **tenants toestaan/blokkeren** het tabblad Bestanden en klik vervolgens op ![ Pictogram blokkeren ](../../media/m365-cc-sc-create-icon.png) **blokkeren.**

3. Configureer **de volgende** instellingen in de flyout Bestanden blokkeren die wordt weergegeven:
   - **Bestandshashes toevoegen:** Voer één SHA256-hashwaarde per regel in, maximaal 20.
   - **Nooit verlopen:** Ga op een van de volgende stappen te werk:
     - Controleer of de instelling is uitgeschakeld (schakel uit) en gebruik het vak Verwijderen aan om de vervaldatum voor de ![ ](../../media/scc-toggle-off.png) vermeldingen op te geven. 

     of

     - Verplaats de schakelknop naar rechts om de items zo te configureren dat ze nooit verlopen: ![Inschakelen](../../media/scc-toggle-on.png).
   - **Optionele opmerking:** Voer beschrijvende tekst in voor de vermeldingen.

4. Wanneer u klaar bent, klikt u op **Toevoegen.**

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Gebruik de Microsoft 365 Defender-portal om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren

**Opmerkingen**:

- Alleen de _combinatie_ van de vervalste _gebruiker_ en de verzendende infrastructuur zoals gedefinieerd in het domeinpaar is specifiek toegestaan of geblokkeerd voor spoofing.
- Wanneer u een invoer toestaan of blokkeren configureert voor een domeinpaar, worden berichten van dat domeinpaar niet meer weergegeven in het inzicht van de spoof intelligence.
- Vermeldingen voor vervalste afzenders verlopen nooit.

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** regels \> **Bedreigingsbeleidsregels** sectie \>  Tenant \> **Allow/Block Lists**.

2. Selecteer op de pagina Lijst met tenants **toestaan/blokkeren** het tabblad **Spoofing** en klik vervolgens op ![ Pictogram Toevoegen ](../../media/m365-cc-sc-create-icon.png) **blokkeren.**

3. Configureer **de volgende** instellingen in het fly-out Nieuwe domeinparen toevoegen dat wordt weergegeven:
   - **Nieuwe domeinparen toevoegen met jokertekens:** Voer één domeinpaar per regel in, maximaal 20. Zie de syntaxis van het domeinpaar voor vervalste afzendergegevens in de sectie [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) verderop in dit artikel voor meer informatie over de syntaxis van vervalste afzenders.
   - **Type spoof:** Selecteer een van de volgende waarden:
     - **Intern:** De vervalste afzender is een domein dat deel uitmaken van uw organisatie (een [geaccepteerd domein).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Extern:** De vervalste afzender is een extern domein.
   - **Actie:** Selecteer **Toestaan** of **Blokkeren.**

4. Wanneer u klaar bent, klikt u op **Toevoegen.**

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a>Gebruik de Microsoft 365 Defender-portal om items in de tenantlijst toestaan/blokkeren weer te geven

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** regels \> **Bedreigingsbeleidsregels** sectie \>  Tenant \> **Allow/Block Lists**.

2. Selecteer het beste tabblad. De beschikbare kolommen zijn afhankelijk van het tabblad dat u hebt geselecteerd:

   - **URL's**:
     - **Waarde:** De URL.
     - **Actie**: Het **waardeblok**.
     - **Laatst bijgewerkt**
     - **Verwijderen aan**
     - **Opmerkingen**
   - **Bestanden**
     - **Waarde:** De bestandshash.
     - **Actie**: Het **waardeblok**.
     - **Laatst bijgewerkt**
     - **Verwijderen aan**
     - **Opmerkingen**
   - **Spoofing**
     - **Vervalste gebruiker**
     - **Verzendende infrastructuur**
     - **Spooftype:** De waarde **Intern** of **Extern**.
     - **Actie:** De waarde **Blokkeren of** **Toestaan.**

   U kunt op een kolomkoppen klikken om in oplopende of aflopende volgorde te sorteren.

   U kunt klikken op **Groep om** de resultaten te groepen. De waarden die beschikbaar zijn, zijn afhankelijk van het tabblad dat u hebt geselecteerd:

   - **URL's:** U kunt de resultaten groepen op **Actie.**
   - **Bestanden:** U kunt de resultaten groepren op **Actie.**
   - **Spoofing:** U kunt de resultaten groeperen op **Actie** of **Spooftype.**

   Klik **op Zoeken,** voer een hele of een deel van een waarde in en druk vervolgens op Enter om een specifieke waarde te zoeken. Wanneer u klaar bent, klikt u op ![ Zoekpictogram Zoeken ](../../media/m365-cc-sc-close-icon.png) **verwijderen.**

   Klik **op Filteren** om de resultaten te filteren. De waarden die beschikbaar zijn in **de flyout Filter** die wordt weergegeven, zijn afhankelijk van het tabblad dat u hebt geselecteerd:

   - **URL's**
     - **Actie**
     - **Nooit verlopen**
     - **Laatst bijgewerkte datum**
     - **Verwijderen aan**
   - **Bestanden**
     - **Actie**
     - **Nooit verlopen**
     - **Laatst bijgewerkt**
     - **Verwijderen aan**
   - **Spoofing**
     - **Actie**
     - **Spooftype**

   Wanneer u klaar bent, klikt u op **Toepassen.** Als u bestaande filters wilt wissen, klikt u **op Filter** en klikt u in het **fly-out** Filter dat wordt weergegeven op Filters **wissen.**

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a>Gebruik de Microsoft 365 Defender-portal om items in de tenantlijst toestaan/blokkeren te wijzigen

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** regels \> **Bedreigingsbeleidsregels** sectie \>  Tenant \> **Allow/Block Lists**.

2. Selecteer het tabblad met het type vermelding dat u wilt wijzigen:
   - **URL's**
   - **Bestanden**
   - **Spoofing**

3. Selecteer het item dat u wilt wijzigen en klik vervolgens op ![ Pictogram ](../../media/m365-cc-sc-edit-icon.png) Bewerken. De waarden die u kunt wijzigen in het flyout dat wordt weergegeven, zijn afhankelijk van het tabblad dat u in de vorige stap hebt geselecteerd:
   - **URL's**
     - **Nooit verlopen** en/of vervaldatum.
     - **Optionele notitie**
   - **Bestanden**
     - **Nooit verlopen** en/of vervaldatum.
     - **Optionele notitie**
   - **Spoofing**
     - **Actie:** U kunt de waarde wijzigen in **Toestaan** of **Blokkeren.**
4. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a>Gebruik de Microsoft 365 Defender-portal om items te verwijderen uit de lijst Tenant Allow/Block

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** regels \> **Bedreigingsbeleidsregels** sectie \>  Tenant \> **Allow/Block Lists**.

2. Selecteer het tabblad met het type invoer dat u wilt verwijderen:
   - **URL's**
   - **Bestanden**
   - **Spoofing**

3. Selecteer het item dat u wilt verwijderen en klik vervolgens op ![ Pictogram ](../../media/m365-cc-sc-delete-icon.png) **verwijderen**.

4. Klik in het waarschuwingsvenster dat wordt weergegeven op **Verwijderen.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om de lijst met tenants toestaan/blokkeren te configureren

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>PowerShell gebruiken om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om blokbestands- of URL-vermeldingen toe te voegen aan de lijst Tenant toestaan/blokkeren:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

In dit voorbeeld wordt een blokbestandsinvoer toegevoegd voor de opgegeven bestanden die nooit verlopen.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

In dit voorbeeld wordt een blok-URL-vermelding voor contoso.com en alle subdomeinen (bijvoorbeeld contoso.com, www.contoso.com en xyz.abc.contoso.com). Omdat we de parameters Vervaldatum of NoExpiration niet hebben gebruikt, verloopt de vermelding na 30 dagen.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Zie [New-TenantAllowBlockListItems voor](/powershell/module/exchange/new-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>PowerShell gebruiken om vervalste afzendergegevens toe te voegen of te blokkeren aan de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om vervalste afzendergegevens toe te voegen aan de lijst Tenant Allow/Block:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Zie [New-TenantAllowBlockListSpoofItems voor](/powershell/module/exchange/new-tenantallowblocklistspoofitems)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om blokbestands- of URL-items weer te geven in de lijst Tenant Allow/Block

Als u blokbestands- of URL-vermeldingen wilt weergeven in de lijst Tenant toestaan/blokkeren, gebruikt u de volgende syntaxis:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

In dit voorbeeld worden gegevens voor de opgegeven waarde voor bestandshash als resultaat gegeven.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

In dit voorbeeld worden alle geblokkeerde URL's als retourneert.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Zie [Get-TenantAllowBlockListItems voor](/powershell/module/exchange/get-tenantallowblocklistitems)gedetailleerde syntaxis en parametergegevens.

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om vervalste afzendergegevens weer te geven in de lijst Tenant Allow/Block:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

Dit voorbeeld retourneert alle vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren.

```powershell
Get-TenantAllowBlockListSpoofItems
```

Dit voorbeeld retourneert alle toegestane vermeldingen van vervalste afzenders die intern zijn.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

In dit voorbeeld worden alle geblokkeerde vermeldingen van vervalste afzenders die extern zijn, als retourneert.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Zie [Get-TenantAllowBlockListSpoofItems (Get-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/get-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om blokbestands- en URL-items in de lijst Tenant allow/block te wijzigen

Gebruik de volgende syntaxis om blokbestands- en URL-vermeldingen in de lijst Tenant toestaan/blokkeren te wijzigen:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

In dit voorbeeld wordt de vervaldatum van de opgegeven blok-URL-vermelding gewijzigd.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Zie [Set-TenantAllowBlockListItems (Set-TenantAllowBlockListItems)](/powershell/module/exchange/set-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren in de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om vervalste afzendergegevens in de lijst Tenant Allow/Block te wijzigen:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

In dit voorbeeld wordt de vermelding van vervalste afzenders gewijzigd in toestaan om te blokkeren.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Zie [Set-TenantAllowBlockListSpoofItems (Set-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/set-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>PowerShell gebruiken om URL- of bestandsgegevens te verwijderen uit de lijst Tenant toestaan/blokkeren

Gebruik de volgende syntaxis om bestands- en URL-vermeldingen te verwijderen uit de lijst Tenant toestaan/blokkeren:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

In dit voorbeeld wordt de opgegeven blok-URL-vermelding verwijderd uit de lijst Tenant toestaan/blokkeren.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Zie [Remove-TenantAllowBlockListItems (Verwijderen-TenantAllowBlockListItems)](/powershell/module/exchange/remove-tenantallowblocklistitems)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>PowerShell gebruiken om vervalste afzenders toe te staan of te blokkeren uit de tenantlijst toestaan/blokkeren

Gebruik de volgende syntaxis als u spoofing sender items wilt verwijderen uit de tenant allow/block list:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Zie [Remove-TenantAllowBlockListSpoofItems (Verwijderen-TenantAllowBlockListSpoofItems)](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)voor gedetailleerde syntaxis- en parametergegevens.

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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Syntaxis van domeinparen voor vervalste afzendergegevens in de lijst Tenant toestaan/blokkeren

Een domeinpaar voor een vervalste afzender in de lijst Tenant toestaan/blokkeren gebruikt de volgende syntaxis: `<Spoofed user>, <Sending infrastructure>` .

- **Vervalste gebruiker:** Deze waarde betreft het e-mailadres van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients. Dit adres wordt ook wel het adres `5322.From` genoemd. Geldige waarden zijn:
  - Een afzonderlijk e-mailadres (bijvoorbeeld chris@contoso.com).
  - Een e-maildomein (bijvoorbeeld contoso.com).
  - Het jokerteken \* (bijvoorbeeld).

- **Verzendende infrastructuur:** deze waarde geeft de bron aan van berichten van de vervalste gebruiker. Geldige waarden zijn:
  - Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver (bijvoorbeeld fabrikam.com).
  - Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).

Hier zijn enkele voorbeelden van geldige domeinparen om vervalste afzenders te identificeren:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Het maximum aantal vervalste afzenders is 1000.

Als u een domeinpaar toevoegt, wordt  de *combinatie* van de vervalste gebruiker en de verzendende infrastructuur alleen mogelijk of blokkeert. E-mail van de vervalste gebruiker van welke bron dan ook is niet toegestaan en e-mail uit de bron van de verzendende infrastructuur wordt niet toegestaan voor vervalste gebruikers. 

U voegt bijvoorbeeld een toegestane vermelding toe voor het volgende domeinpaar:

- **Domein:** gmail.com
- **Infrastructuur**: tms.mx.com

Alleen berichten uit dat domein *en het* verzenden van infrastructuurparen mogen spoofen. Andere afzenders die proberen te spoofen gmail.com zijn niet toegestaan. Berichten van afzenders in andere domeinen die afkomstig zijn van tms.mx.com worden gecontroleerd door spoof intelligence.
