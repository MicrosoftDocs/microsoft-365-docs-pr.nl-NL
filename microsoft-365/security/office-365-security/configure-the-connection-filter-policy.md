---
title: Het standaardfilterbeleid configureren
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
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u verbindingsfiltering configureert in Exchange Online Protection (EOP) om e-mails van e-mailservers toe te staan of te blokkeren.
ms.openlocfilehash: 14758161f827cf231a8f3a0415748c7a2dd5981f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616588"
---
# <a name="configure-connection-filtering"></a>Filteren van verbinding configureren

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige EOP-klant (Exchange Online Protection) zonder Exchange Online-postvakken, gebruikt u verbindingsfiltering in EOP (met name het standaardbeleid voor verbindingsfilter) om goede of slechte bron e-mailservers te identificeren op basis van hun IP-adressen. De belangrijkste onderdelen van het standaardfilterbeleid voor verbindingen zijn:

- **LIJST MET IP-toestaan:** Spamfilters overslaan voor alle binnenkomende berichten van de brone-mailservers die u opgeeft op IP-adres of IP-adresbereik. Zie de [scenario's waarin berichten uit bronnen in de LIJST met IP-toestaan](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) later in dit onderwerp nog steeds worden gefilterd voor scenario's waarin spamfiltering nog steeds kan plaatsvinden op berichten uit deze bronnen. Zie [Veilige afzenderlijsten maken in EOP voor](create-safe-sender-lists-in-office-365.md)meer informatie over hoe de LIJST met IP-toestaan moet passen in uw algemene strategie voor veilige afzenders.

- **IP-bloklijst:** Blokkeer alle binnenkomende berichten van de brone-mailservers die u opgeeft op IP-adres of IP-adresbereik. De binnenkomende berichten worden afgewezen, worden niet gemarkeerd als spam en er vindt geen extra filtering plaats. Zie [Lijsten met blokver afzenders maken in EOP voor](create-block-sender-lists-in-office-365.md)meer informatie over hoe de IP-bloklijst moet passen in uw algemene strategie voor geblokkeerde afzenders.

- **Veilige lijst**: De *veilige lijst* is een dynamische lijst met toegestaneen in het Microsoft-datacenter waarvoor geen klantconfiguratie vereist is. Microsoft identificeert deze vertrouwde e-mailbronnen van abonnementen op verschillende lijsten van derden. U schakelt het gebruik van de veilige lijst in of uit; u de brone-mailservers in de veilige lijst niet configureren. Spamfilters worden overgeslagen op binnenkomende berichten van de e-mailservers op de veilige lijst.

In dit onderwerp wordt beschreven hoe u het standaardfilterbeleid voor verbindingsfilter configureert in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken). Zie [Antispambeveiliging](anti-spam-protection.md)voor meer informatie over hoe EOP verbindingfiltering gebruikt.

> [!NOTE]
> De LIJST MET IP-toestaan, de veilige lijst en de IP-bloklijst maken deel uit van uw algemene strategie om e-mail in uw organisatie toe te staan of te blokkeren. Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) en Lijsten met [geblokkeerde afzenders maken voor](create-block-sender-lists-in-office-365.md)meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u het standaardfilterbeleid voor verbindingen wilt wijzigen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot het standaardbeleid voor verbindingsfilters moet u lid zijn van de rolgroep **Beveiligingslezer.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Als u de ip-adressen van de bron wilt vinden van de e-mailservers (afzenders) die u wilt toestaan of blokkeren, u het kopveld aansluitende IP **(CIP)** in de berichtkop controleren. Zie [Internetberichtenkoppen weergeven in Outlook als](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)u een berichtkoptekst in verschillende e-mailclients wilt weergeven.

- De LIJST MET IP-toestaan heeft voorrang op de IP-bloklijst (een adres op beide lijsten wordt niet geblokkeerd).

- De IP Allow List en de IP Block List ondersteunen elk maximaal 1273 vermeldingen, waarbij een vermelding één IP-adres, een IP-adresbereik of een CIDR-IP (Classless InterDomain Routing) is.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Gebruik het Security & Compliance Center om het standaardfilterbeleid voor verbindingen te wijzigen

1. In het Security & Compliance Center en ga naar **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Vouw op de pagina **Antispaminstellingen** **het filterbeleid Verbinding** uit door op pictogram uitvouwen te klikken ![ en klik ](../../media/scc-expand-icon.png) vervolgens op Beleid **bewerken**.

3. Configureer een van de volgende instellingen in de **standaard** flyout die wordt weergegeven:

   - **Beschrijving**: Voer optionele beschrijvende tekst in.

   - **LIJST MET IP-toestaan:** klik op **Bewerken**. Voer in de flyout **lijst MET IP Toestaan** die wordt weergegeven, een IPV4-adres in het vak Adres of **adresbereik** in met de volgende syntaxis:

     - Enkel IP: bijvoorbeeld 192.168.1.1.

     - IP-bereik: Bijvoorbeeld 192.168.0.1-192.168.0.254.

     - CIDR IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32. Als u spamfilters wilt overslaan voor CIDR-IP-maskerwaarden /1 tot /23, raadpleegt u de [spamfiltering overslaan voor een CIDR-IP buiten de](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) sectie beschikbaar bereik later in dit onderwerp.

     Als u het IP-adres of adresbereik wilt toevoegen, klikt u op Pictogram **toevoegen toevoegen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Als u een item wilt verwijderen, selecteert u de vermelding in **Toegestaan IP-adres** en **klikt** u op Verwijderen verwijderen ![ ](../../media/scc-remove-icon.png) . Klik op **Opslaan** wanneer u gereed bent.

   - **IP-bloklijst**: klik op **Bewerken**. Voer in de flyout **van de IP-bloklijst** die wordt weergegeven, één IP-bereik, IP-bereik of CIDR-ip in het vak **Adres of adresbereik** in zoals eerder beschreven in de instelling **LIJST IP toestaan.**

     Als u het IP-adres of adresbereik wilt toevoegen, klikt u op Pictogram **toevoegen toevoegen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Als u een item wilt verwijderen, selecteert u de vermelding in **Geblokkeerd IP-adres** en **klikt** u op Verwijderen verwijderen ![ ](../../media/scc-remove-icon.png) . Klik op **Opslaan** wanneer u gereed bent.

   - **Veilige lijst inschakelen:** Schakel het gebruik van de veilige lijst in of uit om bekende, goede afzenders te identificeren die spamfilters overslaan.

4. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Gebruik het Security & Compliance Center om het standaardfilterbeleid van de verbinding weer te geven

1. In het Security & Compliance Center en ga naar **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klik op de pagina **Antispaminstellingen** op de vervolgkeuzelijst naast het standaardbeleid met de naam **Verbindingsfilterbeleid**.

3. De beleidsinstellingen worden weergegeven in de vervolgkeuzelijst die wordt geopend.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om het standaardfilterbeleid voor verbindingen te wijzigen

Gebruik de volgende syntaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Opmerkingen**:

- Geldige WAARDEN voor IP-adres of adresbereik zijn:

  - Enkel IP: bijvoorbeeld 192.168.1.1.

  - IP-bereik: Bijvoorbeeld 192.168.0.1-192.168.0.254.

  - CIDR IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32.

- Als u bestaande items wilt *overschrijven* met de waarden die u opgeeft, gebruikt u de volgende syntaxis: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Als u IP-adressen of adresbereiken *wilt toevoegen of verwijderen* zonder dat dit gevolgen heeft voor andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Als u de lijst met IP-toestaan of de LIJST met IP-blokken wilt legen, gebruikt u de waarde `$null` .

In dit voorbeeld worden de LIJST MET IP-toegestaneen en de IP-bloklijst geconfigureerd met de opgegeven IP-adressen en adresbereiken.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In dit voorbeeld worden de opgegeven IP-adressen en adresbereiken toegevoegd en verwijderd uit de LIJST MET IP-toestaan.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Zie [Set-HostedConnectionFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)gedetailleerde syntaxis- en parametergegevens .

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u het standaardfilterbeleid voor verbindingen hebt gewijzigd, voert u een van de volgende stappen uit:

- Ga in het Security & Compliance Center naar **De** \> anti-spam **van bedreigingsbeheer** op de \> **Anti-Spam** \> vervolgkeuzelijst naast **verbindingsfilterbeleid (altijd AAN)** en controleer de instellingen.

- Voer in Exchange Online PowerShell of standalone EOP PowerShell de volgende opdracht uit en verifieer de instellingen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Stuur een testbericht vanuit een vermelding in de LIJST MET IP-toestaan.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Aanvullende overwegingen voor de LIJST MET IP-toegestane

In de volgende secties worden aanvullende items geïdentificeerd die u moet weten wanneer u de LIJST MET IP-toestaan configureert.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Spamfilters overslaan voor een CIDR-IP buiten het beschikbare bereik

Zoals eerder beschreven in dit onderwerp, u alleen gebruik maken van een CIDR IP met het netwerk masker / 24 tot / 32 in de IP Allow List. Als u spamfilters wilt overslaan op berichten van brone-mailservers in het bereik van /1 tot /23, moet u de regels voor exchange-e-mailstroom (ook wel transportregels genoemd) gebruiken. Maar we raden u aan dit niet te doen als dat mogelijk is, omdat de berichten worden geblokkeerd als een IP-adres in het /1-/23 CIDR IP-bereik op een van de eigen of externe bloklijsten van Microsoft wordt weergegeven.

Nu u volledig op de hoogte bent van de mogelijke problemen, u een e-mailstroomregel maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van deze IP-adressen spamfilters overslaan:

- Regelvoorwaarde: **Pas deze regel toe als** het \> IP-adres van de **afzender** zich in een van deze \> **bereiken bevindt of precies overeenkomt** \> (voer uw CIDR-IP in met een /1-/23-netwerkmasker).

- Regelactie: **de berichteigenschappen wijzigen** Stel het \> **spamvertrouwensniveau (SCL)** \> **spamfiltering**in.

U de regel controleren, de regel testen, de regel activeren gedurende een bepaalde periode en andere selecties. We raden u aan de regel een periode te testen voordat u deze afdwingt. Zie [Regels voor e-mailstroom beheren in Exchange Online voor](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)meer informatie.

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Spamfiltering op selectieve e-maildomeinen overslaan vanaf dezelfde bron

Als u doorgaans een IP-adres of adresbereik toevoegt aan de LIJST MET IP-toestaan, vertrouwt u alle binnenkomende berichten uit die e-mailbron. Maar wat als die bron e-mail verzendt vanuit meerdere domeinen en u spamfiltering voor sommige van die domeinen wilt overslaan, maar niet voor andere? U de IP Allow List niet alleen gebruiken om dit te doen, maar u de IP-lijst toestaan gebruiken in combinatie met een e-mailstroomregel.

De brone-mailserver 192.168.1.25 verzendt bijvoorbeeld e-mail van de domeinen contoso.com, fabrikam.com en tailspintoys.com, maar u wilt alleen spamfilters overslaan voor berichten van afzenders in fabrikam.com. Gebruik hiervoor de volgende stappen:

1. Voeg 192.168.1.25 toe aan de LIJST MET IP-toestaan.

2. Een e-mailstroomregel configureren met de volgende instellingen (minimaal):

   - Regelvoorwaarde: **Pas deze regel toe als** het \> IP-adres van de **afzender** zich in een van deze \> **bereiken bevindt of precies overeenkomt met** \> 192.168.1.25 (hetzelfde IP-adres of adresbereik dat u in de vorige stap aan de IP-lijst voor toestaan hebt toegevoegd).

   - Regelactie: **de berichteigenschappen wijzigen** Stel het \> **spamvertrouwensniveau (SCL)** in \> **0**.

   - Regeluitzondering: **het** \> **afzenderdomein is** \> fabrikam.com (alleen het domein of de domeinen die u spamfiltering wilt overslaan).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenario's waarin berichten uit bronnen in de LIJST MET IP-toestaan nog steeds worden gefilterd

Berichten van een e-mailserver in uw IP Allow List zijn nog steeds onderhevig aan spamfilters in de volgende scenario's:

- Een IP-adres in uw IP Allow List is ook geconfigureerd in een on-premises, IP-gebaseerde inkomende connector in *een* tenant in Microsoft 365 (laten we deze tenant A noemen) **en** Tenant A en de EOP-server die het bericht voor het eerst tegenkomt, bevinden zich in *hetzelfde* Active Directory-forest in de Microsoft-datacenters. In dit scenario *wordt* **IPV:CAL** toegevoegd aan de [antispamberichtenkoppen](anti-spam-message-headers.md) van het bericht (met vermelding van het bericht dat spamfilters worden omzeild), maar het bericht is nog steeds onderhevig aan spamfiltering.

- Uw tenant die de IP Allow List en de EOP-server bevat die het bericht voor het eerst tegenkomt, bevindt zich toevallig in *verschillende* Active Directory-forests in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL** *niet* toegevoegd aan de berichtkoppen, zodat het bericht nog steeds onderhevig is aan spamfilters.

Als u een van deze scenario's tegenkomt, u een e-mailstroomregel maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van de problematische IP-adressen spamfiltering overslaan:

- Voorwaarde voor de regel: **Pas deze regel toe als** het \> IP-adres van de **afzender** zich in een van deze \> **bereiken bevindt of precies overeenkomt** met \> (uw IP-adres of adres).

- Regelactie: **de berichteigenschappen wijzigen** Stel het \> **spamvertrouwensniveau (SCL)** \> **spamfiltering**in.

## <a name="new-to-microsoft-365"></a>Nieuw bij Microsoft 365?

||
|:-----|
|![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Ontdek gratis videocursussen voor **admins en IT-professionals,** aangeboden door LinkedIn Learning.|
