---
title: Het standaardbeleid voor verbindingsfilters configureren
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
description: Beheerders kunnen informatie krijgen over het configureren van verbindingsfilters in Exchange Online Protection (EOP) om e-mailberichten van e-mailservers toe te staan of te blokkeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6ec8b4adcdda692ee561f7d50bacf0511642269
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290043"
---
# <a name="configure-connection-filtering"></a>Filteren van verbinding configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige klant van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, gebruikt u verbindingsfiltering in EOP (met name het standaardbeleid voor verbindingsfilters) om goede of slechte bron-e-mailservers aan de IP-adressen te herkennen. De belangrijkste onderdelen van het standaardbeleid voor verbindingsfilters zijn:

- **Lijst met toegestane** IP-adressen: spamfilters overslaan voor alle binnenkomende berichten van de bron-e-mailservers die u opgeeft per IP-adres of IP-adresbereik. Voor scenario's waarin spamfilters mogelijk nog steeds worden uitgevoerd op berichten van deze bronnen, bekijkt u de scenario's waarin berichten van bronnen in de lijst met toegestane [IP-adressen](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) nog steeds worden gefilterd verder op het volgende artikel. Zie Lijsten met veilige afzenders maken [in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie over hoe de lijst met toegestane IP-adressen moet passen in uw algemene strategie voor veilige afzenders.

- **Lijst met IP-blokkering:** blokkeer alle inkomende berichten van de bron-e-mailservers die u opgeeft per IP-adres of IP-adresbereik. De binnenkomende berichten worden geweigerd, worden niet gemarkeerd als spam en er worden geen aanvullende filters opgeslagen. Zie Blokkerende afzenderlijsten maken in EOP voor meer informatie over hoe de lijst met IP-blokkeringen in uw algemene strategie voor geblokkeerde afzenders [moet passen.](create-block-sender-lists-in-office-365.md)

- **Veilige lijst:** de *lijst met veilige* gegevens is een dynamische lijst met toegestane gegevens in het Microsoft-datacenter en vereist geen klantconfiguratie. Microsoft identificeert deze vertrouwde e-mailbronnen uit abonnementen op verschillende lijsten van derden. U schakelt het gebruik van de veilige lijst in of uit. kunt u de bron-e-mailservers op de veilige lijst niet configureren. Spamfilters worden overgeslagen op inkomende berichten van de e-mailservers op de veilige lijst.

In dit onderwerp wordt beschreven hoe u het standaardbeleid voor verbindingsfilters configureert in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken). Zie Beveiliging tegen [ongewenste e-mail](anti-spam-protection.md)voor meer informatie over hoe in EOP verbindingsfilters worden gebruikt.

> [!NOTE]
> De lijst met toegestane IP-adressen, de veilige lijst en de lijst met geblokkeerde IP-adressen maken deel uit van uw algemene strategie om e-mail in uw organisatie toe te staan of te blokkeren. Zie Lijsten met veilige afzenders maken [en](create-safe-sender-lists-in-office-365.md) Lijsten met geblokkeerde afzenders [maken voor meer informatie.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u het standaardbeleid voor verbindingsfilters  wilt wijzigen, moet u lid zijn van de rollengroepen Organisatiebeheer of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot het standaardbeleid voor verbindingsfilters moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.** 

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Als u de IP-bronadressen wilt vinden van de e-mailservers (afzenders) die u wilt toestaan of blokkeren, kunt u het koptekstveld IP **(CIP)** voor de verbinding in de berichtkop controleren. Zie Internetberichtkoppen weergeven in Outlook als u een berichtkop in verschillende e-mail clients [wilt weergeven.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- De lijst met toegestane IP-adressen heeft prioriteit boven de lijst met geblokkeerde IP-adressen (een adres op beide lijsten wordt niet geblokkeerd).

- De lijst met toegestane IP-adressen en de lijst met IP-blokkeringen ondersteunen elk maximaal 1273 vermeldingen, waarbij een vermelding bestaat uit één IP-adres, een IP-adresbereik of een CIDR-IP (Classless InterDomain Routing).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Het beveiligings- & om het standaardbeleid voor verbindingsfilters te wijzigen

1. Ga in het & compliancecentrum naar  \> **Risicobeheerbeleid** \> **antispam.**

2. Vouw op **de pagina Antispaminstellingen** het verbindingsfilterbeleid **uit** door op het pictogram Uitvbreken te klikken en vervolgens op Beleid bewerken ![ te ](../../media/scc-expand-icon.png) **klikken.**

3. Configureer **een van** de volgende instellingen in de standaard flyout die wordt weergegeven:

   - **Beschrijving:** voer optionele beschrijvende tekst in.

   - **Lijst met toegestane** IP-adressen: klik **op Bewerken.** Voer in **de flyout** Lijst met ip-adressen die  wordt weergegeven, een IPV4-adres in het vak Adres of adresbereik in met de volgende syntaxis:

     - Enkel IP-adres: bijvoorbeeld 192.168.1.1.

     - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.

     - CIDR-IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32. Als u spamfilters voor CIDR-IP-maskerwaarden /1 tot en met /23 wilt overslaan, kunt u de spamfilters voor een [CIDR-IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) buiten het beschikbare bereik verderonder in dit artikel lezen.

     Als u het IP-adres of adresbereik wilt toevoegen, klikt u op **Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen. Als u een vermelding wilt verwijderen, selecteert u de vermelding bij **Toegestaan IP-adres** en klikt u **op** ![ ](../../media/scc-remove-icon.png) Verwijderen. Klik op **Opslaan** wanneer u gereed bent.

   - **Lijst met IP-blokkeringen:** klik **op Bewerken.** Voer **in** de flyout Lijst met IP-blokkeringen die wordt weergegeven,  één IP-, IP-bereik of CIDR-IP-adres in het vak Adres of adresbereik in, zoals eerder is beschreven in de instelling Lijst met **ip-adressen.**

     Als u het IP-adres of adresbereik wilt toevoegen, klikt u op **Pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) toevoegen. Als u een vermelding wilt verwijderen, selecteert u de vermelding in **het geblokkeerde IP-adres** en klikt u **op** ![ ](../../media/scc-remove-icon.png) Verwijderen. Klik op **Opslaan** wanneer u gereed bent.

   - **Veilige lijst inschakelen:** het gebruik van de lijst met veilige afzenders in- of uitschakelen om bekende, goede afzenders te identificeren die geen spamfilters meer gebruiken.

4. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Het beveiligings- & om het standaardbeleid voor verbindingsfilters weer te geven

1. Ga in het & compliancecentrum naar  \> **Risicobeheerbeleid** \> **antispam.**

2. Klik op **de pagina Antispaminstellingen** op de vervolgkeuzemenu naast het standaardbeleid met de naam **Verbindingsfilterbeleid.**

3. De beleidsinstellingen worden weergegeven in de vervolgkeuzemenu dat wordt geopend.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell of een zelfstandige EOP PowerShell gebruiken om het standaardbeleid voor verbindingsfilters te wijzigen

Gebruik de volgende syntaxis:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Opmerkingen**:

- Geldige waarden voor ip-adressen of adresbereiken zijn:

  - Enkel IP-adres: bijvoorbeeld 192.168.1.1.

  - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.

  - CIDR-IP: Bijvoorbeeld 192.168.0.1/25. Geldige netwerkmaskerwaarden zijn /24 tot en met /32.

- Gebruik *de volgende* syntaxis als u bestaande gegevens wilt overschrijven met de waarden die u opgeeft: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`

- Gebruik *de volgende* syntaxis als u IP-adressen of adresbereiken wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`

- Gebruik de waarde als u de lijst met toegestane IP-adressen of de lijst met IP-blokkeringen wilt leeg `$null` maken.

In dit voorbeeld worden de lijst met toegestane IP-adressen en de lijst met geblokkeerde IP-adressen geconfigureerd met de opgegeven IP-adressen en adresbereiken.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In dit voorbeeld worden de opgegeven IP-adressen en adresbereiken uit de lijst met toegestane IP-adressen toegevoegd en verwijderd.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Zie [Set HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga op een van de volgende stappen te werk om te controleren of u het standaardbeleid voor verbindingsfilters hebt gewijzigd:

- Ga in het & compliancecentrum naar  Beleid voor bedreigingsbeheer antispam en klik op de vervolgkeuzemenu naast Verbindingsfilterbeleid \>  \>  \> **(altijd AAN)** en controleer de instellingen.

- Voer in Exchange Online PowerShell of een zelfstandige EOP PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Een testbericht verzenden vanuit een item in de lijst met toegestane IP-adressen.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Aanvullende overwegingen voor de lijst met toegestane IP-adressen

In de volgende secties vindt u aanvullende items die u moet kennen wanneer u de lijst met toegestane IP-adressen configureert.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Spamfilters overslaan voor een CIDR-IP buiten het beschikbare bereik

Zoals eerder in dit artikel is beschreven, kunt u in de lijst met toegestane IP-adressen alleen een CIDR-IP gebruiken met het netwerkmasker /24 tot /32. Als u spamfilters op berichten van bron-e-mailservers in het bereik /1 tot en met /23 wilt overslaan, moet u Exchange-regels voor de e-mailstroom gebruiken (ook wel transportregels genoemd). U wordt echter aangeraden dit zo mogelijk niet te doen, omdat de berichten worden geblokkeerd als een IP-adres in het CIDR-bereik van /1 tot en met /23 wordt weergegeven op een van de blokkeerlijsten van Microsoft zelf of van derden.

Nu u volledig op de hoogte bent van de mogelijke problemen, kunt u een regel voor de e-mailstroom maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van deze IP-adressen geen spamfilters meer gebruiken:

- Regelvoorwaarde:  Pas deze regel toe als het IP-adres van de afzender in een van deze bereiken valt of precies overeenkomt (voer uw CIDR-IP in met een \>  \>  \> /1 tot en met /23-netwerkmasker).

- Regelactie: **de berichteigenschappen wijzigen** Stel het \> **betrouwbaarheidsniveau voor ongewenste e-mail in (SCL)** \> **Spamfilters omzeilen.**

U kunt de regel controleren, de regel testen, de regel activeren tijdens een bepaalde periode en andere selecties. Het is raadzaam de regel een bepaalde periode te testen voordat u deze afdwingt. Zie [E-mailstroomregels beheren in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Spamfilters overslaan voor selectieve e-maildomeinen van dezelfde bron

Meestal betekent het toevoegen van een IP-adres of adresbereik aan de lijst Toestaan voor IP-adres dat u alle binnenkomende berichten van die e-mailbron vertrouwt. Maar wat gebeurt er als er via deze bron e-mail vanuit meerdere domeinen wordt verzonden en u spamfilters wilt overslaan voor sommige van deze domeinen, maar niet voor andere? U kunt de lijst met toegestane IP-adressen niet alleen gebruiken, maar u kunt de lijst met ip-adressen wel gebruiken in combinatie met een regel voor de e-mailstroom.

Met de bron-e-mailserver 192.168.1.25 wordt bijvoorbeeld e-mail verzonden vanuit de domeinen contoso.com, fabrikam.com en tailspintoys.com, maar u wilt spamfilters alleen overslaan voor berichten van afzenders in fabrikam.com. Gebruik hiervoor de volgende stappen:

1. Voeg 192.168.1.25 toe aan de lijst met toegestane IP-adressen.

2. Configureer een regel voor de e-mailstroom met de volgende instellingen (minimaal):

   - Regelvoorwaarde: Pas deze regel toe als het IP-adres van de afzender zich in een van deze bereiken of precies overeenkomt met  \>  \> 192.168.1.25 (hetzelfde IP-adres **of** adresbereik dat u in de vorige stap hebt toegevoegd aan de lijst met toegestane \> IP-adressen).

   - Regelactie: **De berichteigenschappen wijzigen** Stel het betrouwbaarheidsniveau voor spam in \> **(SCL)** \> **0.**

   - Uitzondering op regel: **het domein van** de fabrikam.com (alleen het domein of de domeinen \>  \> waar u spamfilters wilt overslaan).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenario's waarin berichten uit bronnen in de lijst met toegestane IP-adressen nog steeds worden gefilterd

In de volgende scenario's kunnen berichten van een e-mailserver in de lijst met toegestane IP-adressen nog steeds worden gefilterd op spam:

- Een IP-adres in uw lijst met toegestane IP-adressen wordt ook geconfigureerd in een on-premises, binnenkomende IP-connector *in* een tenant in Microsoft 365 (laten we deze tenant A **noemen)** en tenant A en de EOP-server waar het bericht voor het eerst wordt aangetroffen, bevinden zich beide *in* dezelfde Active Directory-forest in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL**  toegevoegd aan de berichtkoppen tegen [ongewenste e-mail](anti-spam-message-headers.md) (waarin wordt aangegeven dat het bericht geen spamfilters meer heeft), maar het bericht kan nog steeds worden gefilterd op ongewenste e-mail.

- De tenant met de lijst met toegestane IP-adressen en de EOP-server die het bericht het eerst tegenkomt, bevindt zich *in* verschillende Active Directory-forests in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL** *niet* toegevoegd aan de berichtkoppen, waardoor het bericht nog steeds onderhevig is aan spamfilters.

Als u een van deze scenario's tegenkomt, kunt u een e-mailstroomregel maken met de volgende instellingen (minimaal) om ervoor te zorgen dat berichten van de problematische IP-adressen het spamfilter overslaan:

- Regelvoorwaarde: Pas deze **regel toe als** het IP-adres van de afzender zich in een van deze bereiken of precies overeenkomt \>  \>  \> (uw IP-adres of adressen).

- Regelactie: **de berichteigenschappen wijzigen** Stel het \> **betrouwbaarheidsniveau voor ongewenste e-mail in (SCL)** \> **Spamfilters omzeilen.**

## <a name="new-to-microsoft-365"></a>Nieuw bij Microsoft 365?

****

![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nieuw voor Microsoft 365?** Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** aangeboden door LinkedIn Learning.
