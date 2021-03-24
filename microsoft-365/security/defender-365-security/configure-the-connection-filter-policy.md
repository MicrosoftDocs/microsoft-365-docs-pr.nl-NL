---
title: Het standaardbeleid voor verbindingsfilter configureren
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
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u verbindingsfilters configureert in Exchange Online Protection (EOP) om e-mailberichten van e-mailservers toe te staan of te blokkeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b940aadb4ff5f2c4676ac2411ea3e95a25c7855
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058942"
---
# <a name="configure-connection-filtering"></a>Filteren van verbinding configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige EOP-klant (Exchange Online Protection) zonder Exchange Online-postvakken, gebruikt u verbindingsfilters in EOP (met name het standaardbeleid voor verbindingsfilters) om goede of slechte bron-e-mailservers te identificeren met hun IP-adressen. De belangrijkste onderdelen van het standaardbeleid voor verbindingsfilters zijn:

- **IP-lijst toestaan:** spamfilters overslaan voor alle binnenkomende berichten van de bron-e-mailservers die u opgeeft per IP-adres of IP-adresbereik. Zie scenario's waarin berichten uit bronnen in de [lijst](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) met IP-toestaan nog steeds worden gefilterd op berichten uit deze bronnen voor scenario's waarin spamfilters nog steeds worden gefilterd verder in dit artikel. Zie Lijsten met veilige afzenders maken [in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie over de manier waarop de lijst met IP-toestaan moet passen in uw algemene strategie voor veilige afzenders.

- **LIJST MET IP-blokkering:** Blokkeer alle inkomende berichten van de bron-e-mailservers die u opgeeft per IP-adres of IP-adresbereik. De inkomende berichten worden geweigerd, worden niet gemarkeerd als spam en er vindt geen extra filtering plaats. Zie Lijsten met blok afzenders maken [in EOP](create-block-sender-lists-in-office-365.md)voor meer informatie over hoe de LIJST met IP-blokkeringen moet passen in de strategie voor algehele geblokkeerde afzenders.

- **Veilige lijst:** De *veilige lijst* is een dynamische lijst met toegestane gegevens in het Microsoft-datacenter die geen klantconfiguratie vereist. Microsoft identificeert deze vertrouwde e-mailbronnen van abonnementen tot diverse lijsten van derden. U schakelt het gebruik van de veilige lijst in of uit. u kunt de bron-e-mailservers niet configureren in de veilige lijst. Spamfilters worden overgeslagen op inkomende berichten van de e-mailservers in de veilige lijst.

In dit onderwerp wordt beschreven hoe u het standaardbeleid voor verbindingsfilter configureert in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken). Zie [Anti-spambeveiliging](anti-spam-protection.md)voor meer informatie over hoe EOP verbindingsfilters gebruikt die deel uitmaken van de algemene antispaminstellingen van uw organisatie.

> [!NOTE]
> De lijst met IP-toestaan, de veilige lijst en de LIJST met IP-blokkeringen maken deel uit van uw algemene strategie om e-mail in uw organisatie toe te staan of te blokkeren. Zie Lijsten met veilige [afzenders](create-safe-sender-lists-in-office-365.md) maken en Lijsten met geblokkeerde afzenders maken voor [meer informatie.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u het standaardbeleid voor verbindingsfilters wilt wijzigen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot het standaardbeleid voor verbindingsfilters moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Als u de bron-IP-adressen wilt zoeken van de e-mailservers (afzenders) die u wilt toestaan of blokkeren, kunt u het veld ip-koptekst **(CIP)** voor verbinding in de berichtkop controleren. Zie [Internetberichtkoppen](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)weergeven in Outlook als u een berichtkop in verschillende e-mail clients wilt weergeven.

- De LIJST MET TOESTAAN VAN IP heeft voorrang op de LIJST met IP-blokkeringen (een adres op beide lijsten wordt niet geblokkeerd).

- De LIJST MET IP-toestaan en de LIJST met IP-blokkeringen ondersteunen elk een maximum van 1273 items, waarbij een vermelding één IP-adres, een IP-adresbereik of een CIDR-IP (Classless InterDomain Routing) is.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Gebruik het beveiligings- & compliancecentrum om het standaardbeleid voor verbindingsfilters te wijzigen

1. Ga in het & compliancecentrum naar **Threat management** \> **Policy** \> **Anti-Spam**.

2. Vouw op **de pagina Antispaminstellingen** het filterbeleid voor verbinding uit door te klikken op Pictogram Uitv. Klik vervolgens op Beleid  ![ ](../../media/scc-expand-icon.png) **bewerken.**

3. Configureer **een van** de volgende instellingen in het standaard flyout dat wordt weergegeven:

   - **Beschrijving:** Voer optionele beschrijvende tekst in.

   - **LIJST MET TOESTAAN VAN IP:** Klik op **Bewerken.** Voer in **het fly-out** IP Allow List dat wordt weergegeven, een IPV4-adres in het vak **Adres** of adresbereik in met de volgende syntaxis:

     - Enkel IP: bijvoorbeeld 192.168.1.1.

     - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.

     - CIDR IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32. Als u spamfilters voor CIDR IP-maskerwaarden /1 tot en met /23 wilt overslaan, bekijkt u de sectie Spamfilters overslaan voor een [CIDR-IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) buiten het beschikbare bereik verder in dit artikel.

     Als u het IP-adres of adresbereik wilt toevoegen, klikt u **op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen. Als u een item wilt verwijderen, selecteert u de vermelding in **Toegestaan IP-adres** en klikt u vervolgens **op** ![ ](../../media/scc-remove-icon.png) Verwijderen. Klik op **Opslaan** wanneer u gereed bent.

   - **LIJST MET IP-blokkeringen:** Klik op **Bewerken.** Voer in **het fly-out IP-bloklijst** dat wordt weergegeven, één IP-, IP-bereik of CIDR-IP-ip in het vak Adres of adresbereik in, zoals eerder is beschreven in de instelling LIJST met **IP-toestaan.** 

     Als u het IP-adres of adresbereik wilt toevoegen, klikt u **op Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen. Als u een item wilt verwijderen, selecteert u de vermelding in **Geblokkeerd IP-adres** en klikt u vervolgens **op** ![ ](../../media/scc-remove-icon.png) Verwijderen. Klik op **Opslaan** wanneer u gereed bent.

   - **Veilige lijst inschakelen:** Schakel het gebruik van de veilige lijst in of uit om bekende, goede afzenders te identificeren die spamfilters overslaan.

4. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Het beveiligings- & compliancecentrum gebruiken om het standaardbeleid voor verbindingsfilters weer te geven

1. Ga in het & compliancecentrum naar **Threat management** \> **Policy** \> **Anti-Spam**.

2. Klik op **de pagina Antispam-instellingen** op de vervolgkeuzepagina naast het standaardbeleid met de naam **Verbindingsfilterbeleid.**

3. De beleidsinstellingen worden weergegeven in de vervolgkeuzekeuze die wordt geopend.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om het standaardbeleid voor verbindingsfilters te wijzigen

Gebruik de volgende syntaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Opmerkingen**:

- Geldige IP-adres- of adresbereikwaarden zijn:

  - Enkel IP: bijvoorbeeld 192.168.1.1.

  - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.

  - CIDR IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32.

- Als *u bestaande items wilt* overschrijven met de waarden die u opgeeft, gebruikt u de volgende syntaxis: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Als *u IP-adressen of* adresbereiken wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Gebruik de waarde als u de lijst met IP-toegestane of IP-blokkeringen wilt leeg `$null` maken.

In dit voorbeeld worden de lijst met IP-toegestane adressen en de LIJST met IP-blokkeringen geconfigureerd met de opgegeven IP-adressen en adresbereiken.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In dit voorbeeld worden de opgegeven IP-adressen en adresbereiken uit de lijst met IP-toegestane adressen toegevoegd en verwijderd.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Zie [Set-HostedConnectionFilterPolicy (Set-HostedConnectionFilterPolicy)](/powershell/module/exchange/set-hostedconnectionfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u het standaardbeleid voor verbindingsfilters hebt gewijzigd, gaat u als volgt te werk:

- Ga in & Beveiligingscentrum naar Beleid  voor bedreigingsbeheer Antispam klik op de vervolgkeuzekeuze naast Verbindingsfilterbeleid \>  \>  \> **(altijd AAN)** en controleer de instellingen.

- Voer in Exchange Online PowerShell of zelfstandige EOP PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Een testbericht verzenden vanuit een item in de lijst met IP-toegestane gegevens.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Aanvullende overwegingen voor de lijst met ip-toegestane gegevens

In de volgende secties vindt u aanvullende items die u moet weten wanneer u de LIJST met IP-toestaan configureert.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Spamfilters overslaan voor een CIDR-IP buiten het beschikbare bereik

Zoals eerder in dit artikel is beschreven, kunt u alleen een CIDR-IP gebruiken met het netwerkmasker /24 tot en met /32 in de lijst IP-toestaan. Als u spamfilters op berichten van bron-e-mailservers in het bereik /1 tot en met /23 wilt overslaan, moet u Exchange-regels voor e-mailstroom (ook wel transportregels genoemd) gebruiken. We raden u echter aan dit zo mogelijk niet te doen, omdat de berichten worden geblokkeerd als een IP-adres in het IP-bereik van /1 tot en met /23 cidr wordt weergegeven op een van de door Microsoft eigen of door derden eigen blokkeringslijsten.

Nu u volledig op de hoogte bent van de mogelijke problemen, kunt u een e-mailstroomregel maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van deze IP-adressen spamfilters overslaan:

- Regelvoorwaarde: Pas deze **regel** toe als het IP-adres van de afzender zich in een van deze bereikten of exact overeenkomt (voer uw CIDR-IP in met een netwerkmasker van \>  \>  \> /1 tot en met /23).

- Regelactie: **De eigenschappen van berichten wijzigen** Stel het \> **betrouwbaarheidsniveau voor spam (SCL)** \> **Spamfilters omzeilen in.**

U kunt de regel controleren, de regel testen, de regel activeren tijdens een bepaalde periode en andere selecties. Het is raadzaam om de regel een periode te testen voordat u deze afdwingt. Zie Regels voor [e-mailstroom beheren in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)voor meer informatie.

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Spamfilters overslaan op selectieve e-maildomeinen uit dezelfde bron

Als u een IP-adres of adresbereik toevoegt aan de lijst met IP-toegestane adressen, vertrouwt u alle binnenkomende berichten uit die e-mailbron. Maar wat als die bron e-mail verzendt vanuit meerdere domeinen en u spamfilters voor sommige van deze domeinen wilt overslaan, maar andere niet? U kunt de LIJST MET TOESTAAN VAN IP niet alleen gebruiken om dit te doen, maar u kunt wel de LIJST MET TOESTAAN voor IP gebruiken in combinatie met een regel voor e-mailstroom.

De bron-e-mailserver 192.168.1.25 verzendt bijvoorbeeld e-mail vanuit de domeinen contoso.com, fabrikam.com en tailspintoys.com, maar u wilt alleen spamfilters overslaan voor berichten van afzenders in fabrikam.com. Gebruik hiervoor de volgende stappen:

1. Voeg 192.168.1.25 toe aan de LIJST MET TOESTAAN VAN IP.

2. Configureer een e-mailstroomregel met de volgende instellingen (minimaal):

   - Regelvoorwaarde: Pas deze regel toe als het IP-adres van de afzender zich in een van deze bereiken of exact overeenkomt met  \>  \> 192.168.1.25 (hetzelfde IP-adres **of** adresbereik dat u in de vorige stap hebt toegevoegd aan de lijst met IP-toegestane \> adressen).

   - Actie regel: **de eigenschappen van het bericht wijzigen** Stel het \> **betrouwbaarheidsniveau voor spam (SCL)** \> **0 in.**

   - Regel uitzondering: **Het domein van de** afzender is fabrikam.com (alleen het domein of de domeinen die u \>  \> spamfilters wilt overslaan).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenario's waarin berichten uit bronnen in de lijst met IP-toestaan nog steeds worden gefilterd

Berichten van een e-mailserver in uw lijst met ip-toegestane e-mail zijn nog steeds onderhevig aan spamfilters in de volgende scenario's:

- Een IP-adres in uw lijst met ip-toegestane adressen is ook geconfigureerd in een on-premises, ip-gebaseerde binnenkomende connector *in* een tenant in Microsoft 365 (laten we dit tenant A **noemen)** en Tenant A en de EOP-server die het bericht voor het eerst tegenkomt, bevinden zich in dezelfde *Active* Directory-forest in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL**  toegevoegd aan de antispamberichtenkoppen van het bericht (wat aangeeft dat het bericht spamfilters heeft overgeslagen), maar het bericht is nog steeds onderhevig aan [spamfilters.](anti-spam-message-headers.md)

- Uw tenant met de LIJST MET IP-toestaan en de EOP-server die het bericht voor het eerst tegenkomt, bevindt zich *in* verschillende Active Directory-forests in de Microsoft-datacenters. In dit scenario **wordt IPV:CAL** niet *toegevoegd* aan de berichtkoppen, waardoor het bericht nog steeds onderhevig is aan spamfilters.

Als u een van deze scenario's tegenkomt, kunt u een e-mailstroomregel maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van de problematische IP-adressen spamfilters overslaan:

- Regelvoorwaarde: **Pas deze regel toe als** het IP-adres van de afzender zich in een van deze bereikten of exact overeenkomt \>  \>  \> (uw IP-adres of -adressen).

- Regelactie: **De eigenschappen van berichten wijzigen** Stel het \> **betrouwbaarheidsniveau voor spam (SCL)** \> **Spamfilters omzeilen in.**

## <a name="new-to-microsoft-365"></a>Nieuw bij Microsoft 365?

****

![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** aangeboden door LinkedIn Learning.