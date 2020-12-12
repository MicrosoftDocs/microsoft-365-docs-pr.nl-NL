---
title: Het standaardbeleid voor verbindings filters configureren
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
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen zien hoe het filteren van verbindingen in Exchange Online Protection (EOP) wordt geconfigureerd om e-mailberichten van e-mailservers toe te staan of te blokkeren.
ms.openlocfilehash: 844b1d8d17a99bbb0c441be511c64a009b8dafcb
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659811"
---
# <a name="configure-connection-filtering"></a>Filteren van verbinding configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als u een klant van Microsoft 365 met postvakken in Exchange Online of een zelfstandige Exchange Online Protection (EOP)-klant zonder postvakken van Exchange Online hebt, gebruikt u het filter voor verbindingen in EOP (specifiek het standaardbeleid voor verbindings filters) om goede of ongeldige bron-e-mailservers te identificeren via hun IP-adressen. De belangrijkste onderdelen van het standaardbeleid voor verbindings filters zijn:

- **Lijst met IP-** adressen: Sla spamfilters voor alle binnenkomende berichten op van de bron-e-mailservers die u opgeeft via het IP-adres of het IP-adresbereik. Zie de [scenario's waarin berichten van bronnen in de lijst met toegestane IP-adressen in de lijst met IP-adressen in de lijst met toegestane IP-berichten worden](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) weergegeven, verderop in dit artikel. Zie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie over de manier waarop de lijst met toegestane IP-adressen in uw algemene afzender strategie past.

- **Lijst met IP-blok** keringen: alle inkomende berichten van de bron-e-mailservers die u hebt opgegeven via een IP-adres of IP-adresbereik blokkeren. De inkomende berichten worden geweigerd, worden niet als spam gemarkeerd, en er vindt geen extra filters plaats. Zie [lijsten met geblokkeerde verzenders maken in EOP](create-block-sender-lists-in-office-365.md)voor meer informatie over de manier waarop de lijst met geblokkeerde afzenders in de lijst met geblokkeerde afzenders moet passen.

- **Lijst met veilige lijsten**: de *lijst veilig* is een dynamische lijst met toegestane gebruikers in het Microsoft-datacenter waarvoor geen klant configuratie is vereist. Microsoft identificeert deze vertrouwde e-mail bronnen van abonnementen op diverse lijsten van derden. U schakelt het gebruik van de lijst veilig in of uit. u kunt de bron-e-mailservers in de lijst veilig niet configureren. Filteren van spam wordt overgeslagen op inkomende berichten van de e-mailservers in de lijst veilig.

In dit onderwerp wordt uitgelegd hoe u het standaardbeleid voor verbindings filters configureert in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online). Zie voor meer informatie over het gebruik van EOP verbindingen filteren maakt deel uit van de algemene antispam instellingen van uw organisatie en Zie [antispam beveiliging](anti-spam-protection.md).

> [!NOTE]
> De lijst met IP-toegestane lijsten, veilige lijsten en de lijst met IP-blokken vormen één onderdeel van uw algemene strategie om e-mail in uw organisatie toe te staan of te blokkeren. Zie [lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) en [lijsten met geblokkeerde afzenders](create-block-sender-lists-in-office-365.md)maken voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u het standaardbeleid voor verbindings filters wilt wijzigen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .
  - Voor alleen-lezen toegang tot het standaardbeleid voor verbindings filters moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Als u wilt zoeken naar de bron-IP-adressen van de e-mailservers (afzenders) die u wilt toestaan of blokkeren, kunt u het koptekstveld voor de verbinding van IP (**overschrijving**) controleren in de kop van het e-mailbericht. Zie [internetberichtkoppen weergeven in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)als u een berichtkop wilt weergeven in verschillende e-mailclients.

- De lijst met toegestane IP-adressen heeft voorrang op de lijst met IP-blok regels (een adres in beide lijsten wordt niet geblokkeerd).

- De lijst met toegestane IP-adressen en de lijst met IP-geblokkeerde gegevens zijn maximaal 1273 vermeldingen, waarbij een vermelding één IP-adres, een IP-adresbereik of een Klasloze IP-adres van een router (Classless) IP is.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>U kunt het standaardbeleid voor verbindings filters wijzigen via het compliance-& Beveiligingscentrum

1. Ga in het beveiligings & compliance en ga  naar \>  \> **anti spam** over beleid voor Threat Management.

2. Vouw op de pagina **anti spam instellingen** het **beleid voor verbindings filters** uit door te klikken op het ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) en vervolgens op **beleid bewerken**.

3. Configureer de volgende instellingen in de **standaard** flyout die wordt weergegeven:

   - **Beschrijving**: Voer desgewenst een beschrijvende tekst in.

   - **Lijst met toegestane IP-adressen**: Klik op **bewerken**. Voer in de vervolg **keuzelijst IP-adreslijst** die wordt weergegeven, een IPv4-adres in het vak **adres of adresbereik** in met de volgende syntaxis:

     - Eén IP: bijvoorbeeld 192.168.1.1.

     - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.

     - CIDR IP: bijvoorbeeld 192.168.0.1/25. Geldige waarden voor Netwerkmaskers zijn/24 via/32. Als u het filteren op ongewenste e-mail wilt overslaan voor CIDR IP-masker waarden/1 naar/23, raadpleegt u het [filter voor spam overslaan voor een CIDR-IP buiten het gedeelte beschikbare bereik](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) verderop in dit artikel.

     Als u een IP-adres of adresbereik wilt  toevoegen, klikt u op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Als u een vermelding wilt verwijderen, selecteert u de vermelding in het **toegestane IP-adres** en klikt **u op** ![ verwijderen ](../../media/scc-remove-icon.png) . Klik op **Opslaan** wanneer u gereed bent.

   - **Lijst met IP-blok**: Klik op **bewerken**. Voer in de vervolgkeuzelijst **IP-bloklijst** die wordt weergegeven, één IP-adres, IP-bereik of CIDR IP-adres in in het vak **adres of adresbereik** zoals hierboven is beschreven in de instelling **lijst met toegestane IP-** adressen.

     Als u een IP-adres of adresbereik wilt  toevoegen, klikt u op ![ pictogram toevoegen toevoegen ](../../media/ITPro-EAC-AddIcon.png) . Als u een vermelding wilt verwijderen, selecteert u het item in het **geblokkeerde IP-adres** en klikt **u op** ![ verwijderen ](../../media/scc-remove-icon.png) . Klik op **Opslaan** wanneer u gereed bent.

   - **Veilige lijst inschakelen**: Hiermee kunt u de lijst met veilige afzenders identificeren van bekende, goede afzenders waarmee spamfilters worden overgeslagen.

4. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Het standaardbeleid voor verbindings filters & gebruiken om het standaardbeleid voor verbindings filters te bekijken

1. Ga in het beveiligings & compliance en ga  naar \>  \> **anti spam** over beleid voor Threat Management.

2. Op de pagina **anti spam instellingen** klikt u op de vervolgkeuzelijst naast het standaardbeleid met de naam **verbindings filter beleid**.

3. De beleidsinstellingen worden weergegeven in de vervolgkeuzelijst die wordt geopend.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Het standaardbeleid voor verbindings filters wijzigen met Exchange Online PowerShell of zelfstandige EOP PowerShell

Gebruik de volgende syntaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Opmerkingen**:

- Geldige waarden voor een IP-adres of adresbereik zijn:

  - Eén IP: bijvoorbeeld 192.168.1.1.

  - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.

  - CIDR IP: bijvoorbeeld 192.168.0.1/25. Geldige waarden voor Netwerkmaskers zijn/24 via/32.

- Gebruik de volgende syntaxis om bestaande vermeldingen te *overschrijven* met de waarden die u opgeeft: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Gebruik de volgende syntaxis om IP-adressen of adresbereiken *toe te voegen of te verwijderen* zonder dat dit invloed heeft op andere bestaande vermeldingen: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Als u de lijst met IP-adressen of de lijst met IP-blokletters wilt leegmaken, gebruikt u de waarde `$null` .

In dit voorbeeld wordt de lijst met toegestane IP-adressen en adresbereiken in de lijst met IP-adressen en adresbereiken ingesteld.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In dit voorbeeld worden de opgegeven IP-adressen en adresbereiken in de lijst met toegestane IP-adressen toegevoegd en verwijderd.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Zie [set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Voer een van de volgende stappen uit om te controleren of het standaardbeleid voor verbindings filters is gewijzigd:

- Ga in het beveiligings & compliance **naar** \>  \> **anti-spam** \> op de vervolgkeuzelijst naast **verbindings filter beleid (altijd aan**) en controleer de instellingen.

- Voer in Exchange Online PowerShell of zelfstandige EOP PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Verzend een testbericht van een vermelding in de lijst met toegestane IP-adressen.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Aanvullende overwegingen voor de lijst met toegestane IP-adressen

In de volgende secties worden extra items aangegeven waarover u moet weten wanneer u de lijst met toegestane IP-adressen configureert.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Spam filteren van een CIDR IP buiten het beschikbare bereik overslaan

Zoals eerder in dit artikel wordt beschreven, kunt u alleen een CIDR-IP gebruiken met de netwerkmask/24 naar/32 in de lijst met toegestane IP-adressen. Als u het filter voor ongewenste e-mail wilt gebruiken voor berichten van de bron-e-mailservers in het bereik/1 tot en met 23, moet u Exchange-e-mail stroom regels (ook wel een transportregel genoemd) gebruiken. U wordt aangeraden dit niet te doen als u dit mogelijk doet omdat de berichten worden geblokkeerd als een IP-adres in het IP-bereik van Microsoft of een van de lijsten van derden wordt weergegeven.

Nu u volledig op de hoogte bent van de mogelijke problemen, kunt u een e-mail stroom regel met de volgende instellingen (minimaal) maken om ervoor te zorgen dat berichten van deze IP-adressen worden gefilterd met ongewenste e-mail:

- Voorwaarde van de regel: **deze regel toepassen als** \> **het** \> **IP-adres van de afzender in een van deze bereiken of precies overeenkomen** \> (Voer uw CIDR-IP-netwerkmasker in)

- Actie van de regel: **Wijzig de berichteigenschappen** \> **stellen het vertrouwensniveau voor ongewenste e-mail (SCL)** \> **over om spam te filteren**.

U kunt de regel controleren, de regel testen, de regel activeren gedurende een specifieke periode en andere selecties. U wordt aangeraden de regel te testen voor een periode voordat u deze afdwingt. Zie voor meer informatie [e-mail stroom regels beheren in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Spam filteren van selectief e-mail domeinen uit dezelfde bron

Meestal kunt u een IP-adres of adresbereik toevoegen aan de lijst met IP-adressen, zodat u alle inkomende berichten van die e-mail bron kunt vertrouwen. Maar wat gebeurt er als de bron e-mail van meerdere domeinen verzendt en u ongewenste e-mail wilt overslaan voor sommige van die domeinen, maar niet naar andere? U kunt de lijst met toegestane IP-adressen niet gebruiken, maar u kunt de lijst met toegestane IP-adressen gebruiken in combinatie met een e-mail stroom regel.

Met de bron-e-mailserver 192.168.1.25 wordt bijvoorbeeld e-mail verzonden via de domeinen contoso.com, fabrikam.com en tailspintoys.com, maar u wilt dat alleen spam filteren op berichten van afzenders in fabrikam.com. Voer de volgende stappen uit om dit te doen:

1. Voeg 192.168.1.25 toe aan de lijst met toegestane IP-adressen.

2. Configureer een e-mail stroom regel met de volgende instellingen (minimaal):

   - Voorwaarde van de regel: **deze regel toepassen als** \> **het** \> **IP-adres van de afzender in een van deze bereiken valt of precies overeenkomt** met \> 192.168.1.25 (hetzelfde IP-adres of adresbereik dat u in de vorige stap hebt toegevoegd aan de lijst met toegestane IP-adressen).

   - Actie van de regel: **Wijzig de berichteigenschappen** \> **stellen het betrouwbaarheidsniveau voor ongewenste e-mail (SCL)** \> **0** in.

   - Regel uitzondering: **het domein van de afzender** \> **is** \> fabrikam.com (alleen het domein of de domeinen die u wilt filteren. spam filteren).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenario's waarbij berichten uit bronnen in de lijst met toegestane IP-adressen nog zijn gefilterd

Berichten van een e-mailserver in de lijst met toegestane IP-adressen zijn blijvend voor spamfilters in de volgende scenario's:

- Een IP-adres in uw lijst met toegestane IP-adressen wordt ook geconfigureerd in een on-premises, IP-based inkomende connector in *een* Tenant in microsoft 365 (laten we deze Tenant a noemen) **en** TENANT A en de EOP-server die het bericht voor het eerst aftreffen, treden op *in de micro* Soft-datacenters. In dit scenario wordt **ipv: CAL**  toegevoegd aan de [e-mailbericht koppen](anti-spam-message-headers.md) van het bericht (die aangeven dat het e-mailbericht wordt genegeerd), maar het bericht is nog steeds onderworpen aan spamfilters.

- Uw Tenant met de lijst met IP-adressen en de EOP-server die het bericht voor het eerst afmeldt, komt voor in *verschillende* Active Directory-forests in de Microsoft-datacenters. In dit scenario wordt **ipv: CAL** *niet* toegevoegd aan de berichtkoppen, dus is het bericht nog steeds onderworpen aan spamfilters.

Als u een van deze scenario's ondervindt, kunt u een e-mail stroom regel met de volgende instellingen (minimaal) maken om ervoor te zorgen dat berichten van de problematische IP-adressen worden gebruikt om spam te filteren.

- Voorwaarde van de regel: **pas deze regel toe als** \> **het** \> **IP-adres van de afzender in een van deze bereiken of precies overeenkomt met** \> uw IP-adres of adres.

- Actie van de regel: **Wijzig de berichteigenschappen** \> **stellen het vertrouwensniveau voor ongewenste e-mail (SCL)** \> **over om spam te filteren**.

## <a name="new-to-microsoft-365"></a>Nieuw bij Microsoft 365?

****

![Het kleine pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nieuw bij microsoft 365?** Ontdek gratis video cursussen voor **Microsoft 365-beheerders en IT-professionals**, aangeboden via LinkedIn learning.
