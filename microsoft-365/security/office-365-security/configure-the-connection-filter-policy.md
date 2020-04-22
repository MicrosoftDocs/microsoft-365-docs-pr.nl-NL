---
title: Het standaardverbindingsfilterbeleid, IP-lijst met toegestane gegevens, IP-bloklijst configureren, veilige lijst in- of uitschakelen
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
description: U het verbindingsfilterbeleid gebruiken om een lijst met IP-adressen die u vertrouwt, te gebruiken om ervoor te zorgen dat e-mail die wordt verzonden van mensen die u vertrouwt, niet wordt geblokkeerd. U ook een IP-bloklijst met geblokkeerde afzenders maken.
ms.openlocfilehash: 54e68c79f78bb1408684ac583edff137cb687b53
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637744"
---
# <a name="configure-connection-filtering"></a>Verbindingsfiltering configureren

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection (EOP)-klant zonder Exchange Online-postvakken, gebruikt u verbindingsfiltering in EOP (met name het standaardverbindingsfilterbeleid) om goede of slechte brone-mailservers te identificeren op hun IP-adressen. De belangrijkste onderdelen van het standaardverbindingsfilterbeleid zijn:

- **LIJST met IP-regels:** Spamfilters overslaan voor alle binnenkomende berichten van de brone-mailservers die u opgeeft op IP-adres of IP-adresbereik. Zie de [scenario's waarin berichten van bronnen in de lijst met IP-toestaan](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) later in dit onderwerp nog steeds worden gefilterd voor scenario's waarin spamfiltering mogelijk nog steeds plaatsvindt op berichten uit deze bronnen. Zie Lijsten met [veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)voor meer informatie over hoe de lijst met IP-toegestane gegevens moet passen in uw algemene strategie voor veilige afzenders.

- **IP-bloklijst:** blokkeer alle binnenkomende berichten van de bron-e-mailservers die u opgeeft op IP-adres of IP-adresbereik. De binnenkomende berichten worden geweigerd, worden niet gemarkeerd als spam en er vindt geen extra filtering plaats. Zie Lijsten met [blokafzenders maken in Office 365](create-block-sender-lists-in-office-365.md)voor meer informatie over hoe de IP-bloklijst moet passen in uw algemene strategie voor geblokkeerde afzenders.

- **Veilige lijst:** De *veilige lijst* is een lijst met dynamische toegestane in het Microsoft-datacenter waarvoor geen klantconfiguratie vereist is. Microsoft identificeert deze vertrouwde e-mailbronnen van abonnementen op verschillende lijsten van derden. U schakelt het gebruik van de veilige lijst in of uit; u de brone-mailservers in de veilige lijst niet configureren. Spamfiltering wordt overgeslagen bij binnenkomende berichten van de e-mailservers op de veilige lijst.

In dit onderwerp wordt beschreven hoe u het standaardverbindingsfilterbeleid configureert in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten). Zie [Antispambeveiliging](anti-spam-protection.md)voor meer informatie over hoe EOP verbindingfiltering gebruikt.

> [!NOTE]
> De LIJST met IP-toegestane, de veilige lijst en de IP-bloklijst maken deel uit van uw algemene strategie om e-mail toe te staan of te blokkeren in uw organisatie. Zie [Lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) en Lijsten met [geblokkeerde afzenders maken](create-block-sender-lists-in-office-365.md)voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u het standaardverbindingsfilterbeleid wilt wijzigen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot het standaardverbindingsfilterbeleid moet u lid zijn van de rolgroep **Beveiligingslezer.** Zie Machtigingen in het Security & Compliance [Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rolgroepen in het Security & Compliance Center.

- Als u de bron-IP-adressen wilt vinden van de e-mailservers (afzenders) die u wilt toestaan of blokkeren, u het koptekstveld verbinding maken met IP **(CIP)** in de berichtkop. Zie [Kopteksten voor internetberichten weergeven in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)als u een berichtkopin in verschillende e-mailclients wilt weergeven.

- De IP-lijst met toegestane heeft voorrang op de IP-bloklijst (een adres op beide lijsten wordt niet geblokkeerd).

- De IP-lijst met toegestane en de IP-bloklijst ondersteunen elk maximaal 1273 vermeldingen, waarbij een item één IP-adres, een IP-adresbereik of een CIDR-IP (Classless InterDomain Routing) is.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Het beveiligingscentrum & compliancecenter gebruiken om het standaardbeleid voor verbindingsfilter te wijzigen

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-Spam**.

2. Vouw op de pagina **Instellingen voor antispam** ![het](../../media/scc-expand-icon.png) **filterbeleid van verbinding** uit door op Pictogram Uitvouwen te klikken en klik vervolgens op **Beleid bewerken**.

3. Configureer in de **standaardflyout** die wordt weergegeven een van de volgende instellingen:

   - **Beschrijving**: Voer optionele beschrijvende tekst in.

   - **Lijst met IP-toestaan**: Klik op **Bewerken**. Voer in de flyout van de **lijst IP-lijst toestaan** die wordt weergegeven, een IPV4-adres in het vak **Adres of adresbereik** in met de volgende syntaxis:

     - Single IP: Bijvoorbeeld 192.168.1.1.

     - IP-bereik: Bijvoorbeeld 192.168.0.1-192.168.0.254.

     - CIDR IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32. Zie [het filteren van spam voor een CIDR-IP-masker later](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) in dit onderwerp om spamfilters voor CIDR-ip over te slaan voor CIDR-ip.

     Als u het IP-adres- **Add** ![of](../../media/ITPro-EAC-AddIcon.png)adresbereik wilt toevoegen, klikt u op Pictogram toevoegen . Als u een item wilt verwijderen, selecteert u het](../../media/scc-remove-icon.png)item in Toegestaan **IP-adres** en klikt u op **Verwijderen** ![. Klik op **Opslaan** wanneer u gereed bent.

   - **IP-bloklijst:** klik op **Bewerken**. Voer in de flyout **van de IP-bloklijst** die wordt weergegeven, één IP-, IP-bereik of CIDR-IP in het vak **Adres- of adresbereik** in, zoals eerder beschreven in de instelling **Lijst met IP-lijst toestaan.**

     Als u het IP-adres- **Add** ![of](../../media/ITPro-EAC-AddIcon.png)adresbereik wilt toevoegen, klikt u op Pictogram toevoegen . Als u een item wilt verwijderen, selecteert u het](../../media/scc-remove-icon.png)item in geblokkeerd **IP-adres** en klikt u op **Verwijderen** ![. Klik op **Opslaan** wanneer u gereed bent.

   - **Schakel een veilige lijst in:** Schakel het gebruik van de veilige lijst in of uit om bekende, goede afzenders te identificeren die spamfilters overslaan.

4. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Het beveiligingscentrum & compliancecenter gebruiken om het standaardbeleid voor verbindingsfilter weer te geven

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-Spam**.

2. Klik op de pagina **Antispaminstellingen** op de vervolgkeuzelijst naast het standaardbeleid met de naam **Verbindingsfilterbeleid**.

3. De beleidsinstellingen worden weergegeven in de vervolgkeuzelijst die wordt geopend.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell gebruiken om het standaardbeleid voor verbindingsfilter te wijzigen

Gebruik de volgende syntaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Opmerkingen**:

- Geldige IP-adres- of adresbereikwaarden zijn:

  - Single IP: Bijvoorbeeld 192.168.1.1.

  - IP-bereik: Bijvoorbeeld 192.168.0.1-192.168.0.254.

  - CIDR IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32.

- Als u bestaande vermeldingen met de opgegeven waarden wilt `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` *overschrijven,* gebruikt u de volgende syntaxis: .

- Als u IP-adressen of adresbereiken *wilt toevoegen of verwijderen* zonder `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`dat dit gevolgen heeft voor andere bestaande vermeldingen, gebruikt u de volgende syntaxis: .

- Als u de lijst met IP-toegestane `$null`of IP-bloklijst wilt legen, gebruikt u de waarde .

In dit voorbeeld worden de lijst met IP-toegestane en de IP-bloklijst geconfigureerd met de opgegeven IP-adressen en adresbereiken.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In dit voorbeeld worden de opgegeven IP-adressen en adresbereiken toegevoegd en verwijderd uit de lijst met IP-toegestane adressen.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Zie [Set-HostedConnectionFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy)gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga een van de volgende stappen uit om te controleren of u het standaardbeleid voor verbindingsfilter hebt gewijzigd:

- Ga in het Beveiligings- & Compliance Center naar **Bedreigingsbeheerbeleid** \> **Policy** \> **Anti-Spam** \> klik op de vervolgkeuzelijst naast **Het filterbeleid van Verbinding (altijd aan)** en controleer de instellingen.

- Voer in Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Een testbericht verzenden vanuit een item op de lijst met IP-toegestane.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Aanvullende overwegingen voor de lijst met IP-toegestane

In de volgende secties worden aanvullende items geïdentificeerd die u moet weten wanneer u de lijst met IP-toegestane items configureert.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Spamfiltering overslaan voor een CIDR-IP buiten het beschikbare bereik

Zoals eerder beschreven in dit onderwerp, u alleen een CIDR IP gebruiken met het netwerkmasker /24 tot /32 in de IP-lijst met toegestane gegevens. Als u spamfilters wilt overslaan op berichten van brone-mailservers in het bereik van /1 tot /23, moet u de regels voor de e-mailstroom van Exchange gebruiken (ook wel transportregels genoemd). Maar we raden u aan dit niet te doen als dit mogelijk is, omdat de berichten worden geblokkeerd als een IP-adres in het IP-bereik van /1 tot /23 wordt weergegeven op een van microsofts eigen bloklijsten of blokkeringen van derden.

Nu u zich volledig bewust bent van de mogelijke problemen, u een regel voor e-mailstroom maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van deze IP-adressen spamfilters overslaan:

- Regelvoorwaarde: **Pas deze regel toe als** \> het IP-adres van de **afzender** \> **zich in een van deze bereiken bevindt of precies overeenkomt** \> (voer uw CIDR-IP in met een /1 tot /23-netwerkmasker).

- Regelactie: **Wijzig de eigenschappen** \> van het bericht **Stel het spamvertrouwensniveau (SCL)** \> **Spamfiltering in.**

U de regel controleren, de regel testen, de regel activeren tijdens een bepaalde periode en andere selecties. We raden u aan de regel te testen voor een periode voordat u deze afdwingt. Zie [Regels voor e-mailstroom beheren in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)voor meer informatie.

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Spamfiltering op selectieve e-maildomeinen van dezelfde bron overslaan

Als u een IP-adres- of adresbereik toevoegt aan de lijst met IP-toegestane gegevens, vertrouwt u doorgaans alle binnenkomende berichten van die e-mailbron. Maar wat als die bron e-mail van meerdere domeinen verzendt en u spamfiltering voor sommige van die domeinen wilt overslaan, maar andere niet? U de IP-lijst toestaan niet alleen gebruiken om dit te doen, maar u de ip-lijst toestaan gebruiken in combinatie met een regel voor e-mailstroom.

De bron-e-mailserver 192.168.1.25 verzendt bijvoorbeeld e-mail van de domeinen contoso.com, fabrikam.com en tailspintoys.com, maar u wilt alleen spamfilters overslaan voor berichten van afzenders in fabrikam.com. Gebruik hiervoor de volgende stappen:

1. Voeg 192.168.1.25 toe aan de lijst met IP-toegestane.

2. Een regel voor e-mailstroom configureren met de volgende instellingen (minimaal):

   - Regelvoorwaarde: **Pas deze regel toe als** \> het IP-adres van de **afzender** \> **zich in een van deze bereiken bevindt of exact overeenkomt met** \> 192.168.1.25 (hetzelfde IP-adres of adresbereik dat u in de vorige stap aan de lijst met IP-toegestane gegevens hebt toegevoegd).

   - Regelactie: **Wijzig de eigenschappen** \> van het bericht **Stel het spamvertrouwensniveau (SCL)** \> **0**in.

   - Regeluitzondering: **het afzenderdomein** \> **is** \> fabrikam.com (alleen het domein of de domeinen die u wilt overslaan naar spamfilters).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenario's waarin berichten van bronnen in de lijst met IP-toegestane nog steeds worden gefilterd

Berichten van een e-mailserver in uw lijst met IP-toegestane gegevens worden in de volgende scenario's nog steeds gefilterd op spam:

- Een IP-adres in uw IP-lijst met toegestane gegevens is ook geconfigureerd in een on-premises, IP-gebaseerde inkomende connector in *elke* tenant in Microsoft 365 (laten we deze tenant A noemen) **en** Tenant A en de EOP-server die het bericht voor het eerst tegenkomt, bevinden zich toevallig in *hetzelfde* Active Directory-forest in de Microsoft-datacenters. In dit scenario *wordt* **IPV:CAL** toegevoegd aan de [antispamberichtenkoppen](anti-spam-message-headers.md) van het bericht (met vermelding van het bericht dat spamfiltering wordt omzeild), maar is het bericht nog steeds onderhevig aan spamfiltering.

- Uw tenant die de IP-lijst met toegestane gegevens bevat en de EOP-server die het bericht voor het eerst tegenkomt, bevindt zich toevallig in *verschillende* Active Directory-forests in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL** *niet* toegevoegd aan de berichtkoppen, dus het bericht is nog steeds onderhevig aan spamfiltering.

Als u een van deze scenario's tegenkomt, u een regel voor e-mailstroom maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van de problematische IP-adressen spamfilters overslaan:

- Regelvoorwaarde: **Pas deze regel toe als** \> het IP-adres van de **afzender** \> **zich in een van deze bereiken bevindt of precies overeenkomt** \> (uw IP-adres of adressen).

- Regelactie: **Wijzig de eigenschappen** \> van het bericht **Stel het spamvertrouwensniveau (SCL)** \> **Spamfiltering in.**

## <a name="new-to-office-365"></a>Nieuw in Office 365?

||
|:-----|
|![Het korte pictogram voor](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **New to Microsoft 365?** Ontdek gratis videocursussen voor **beheerders en IT-professionals,** die u worden aangeboden door LinkedIn Learning.|
