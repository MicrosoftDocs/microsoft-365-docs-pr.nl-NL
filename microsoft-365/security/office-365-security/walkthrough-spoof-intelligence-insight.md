---
title: Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze het spoof intelligence-beleid en het inzicht in spoof intelligence kunnen gebruiken om gedetecteerde vervalste afzenders toe te staan of te blokkeren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793206"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof intelligence in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> In dit artikel wordt beschreven welke oudere, vervalste afzenderbeheerervaring wordt vervangen. Zie Inzicht in spoof [intelligence in EOP](learn-about-spoof-intelligence.md) voor meer informatie over de nieuwe ervaring

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beschermd tegen spoofing door EOP. EOP gebruikt **spoof intelligence** als onderdeel van de algehele verdediging van uw organisatie tegen phishing. Zie Bescherming tegen spoofing in [EOP voor meer informatie.](anti-spoofing-protection.md)

Het standaardbeleid voor spoof intelligence (en alleen spoof **intelligence)** helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet in de EOP-spamfilters terecht komt en dat uw gebruikers worden beschermd tegen spam- of phishingaanvallen. U kunt ook het inzicht in **spoofinformatie** gebruiken om snel te bepalen welke externe afzenders u legitiem niet-genauteerde e-mail sturen (berichten uit domeinen die niet door SPF-, DKIM- of DMARC-controles worden verzonden).

U kunt spoofinformatie beheren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.
  - Als u rechtstreeks naar de **pagina Anti-spaminstellingen voor** het spoof intelligence-beleid wilt gaan, gebruikt u <https://protection.office.com/antispam> .
  - Als u rechtstreeks naar de pagina **Beveiligingsdashboard wilt** gaan voor het inzicht in spoof intelligence, gebruikt <https://protection.office.com/searchandinvestigation/dashboard> u .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u het spoof intelligence-beleid wilt wijzigen of spoofinformatie wilt in- of uitschakelen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot het spoof intelligence-beleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- De opties voor spoofinformatie worden beschreven in [spoofinstellingen in anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)

- U kunt de instellingen voor spoof intelligence inschakelen, uitschakelen en configureren in anti-phishingbeleid. Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:

  - [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md).
  - [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365.](configure-atp-anti-phishing-policies.md)

- Zie [EOP anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor spoofinformatie.

## <a name="manage-spoofed-senders"></a>Vervalste afzenders beheren

Er zijn twee manieren om vervalste afzenders toe te staan en te blokkeren:

- [Het spoof intelligence-beleid gebruiken](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [Het inzicht in spoof intelligence gebruiken](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>Vervalste afzenders beheren in het beleid voor spoof intelligence

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op ![ Pictogram Uitvvllen ](../../media/scc-expand-icon.png) om **spoofintelligentiebeleid uit te vouwen.**

   ![Het spoof intelligence-beleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Maak een van de volgende selecties:

   - **Nieuwe afzenders controleren**
   - **Laat mij afzenders zien die ik al heb bekeken**

4. Selecteer een van de volgende tabbladen in de fly-out Beslissen of deze **afzenders** uw gebruikers mogen spoofen:

   - **Uw domeinen:** afzenders die gebruikers spoofen in uw interne domeinen.
   - **Externe domeinen:** afzenders die gebruikers spoofen in externe domeinen.

5. Klik ![ op Pictogram ](../../media/scc-expand-icon.png) Uitv in de kolom **Toegestaan om te** vervalsen? Kies **Ja** om de vervalste afzender toe te staan of kies **Nee om** het bericht te markeren als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**). Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings) voor meer informatie.

   ![Schermafbeelding van de spoofed senders flyout en of de afzender mag spoofen](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   De kolommen en waarden die u ziet, worden in de volgende lijst uitgelegd:

   - **Vervalste gebruiker:** het gebruikersaccount dat wordt vervalst. Dit is de afzender van het bericht in het Van-adres (ook wel het adres genoemd) dat `5322.From` wordt weergegeven in e-mail clients. De geldigheid van dit adres wordt niet gecontroleerd door SPF.
     - Op het **tabblad Uw** domeinen bevat de waarde één e-mailadres of als de bron-e-mailserver meerdere gebruikersaccounts vervalst, bevat deze meer **dan één**.
     - Op het **tabblad Externe** domeinen bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.

   - **Verzendende infrastructuur:** het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver. Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).

     Zie Een overzicht van de standaarden voor [e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichtbronnen en afzenders van berichten.

   - **# van berichten:** Het aantal berichten van de verzendende infrastructuur naar uw organisatie dat de opgegeven vervalste afzender of afzenders bevat binnen de afgelopen 30 dagen.

   - **# van gebruikersklachten:** Klachten die door uw gebruikers zijn ingediend tegen deze afzender binnen de afgelopen 30 dagen. Klachten worden meestal in de vorm van ongewenste e-mail ingediend bij Microsoft.

   - **Verificatieresultaat:** Een van de volgende waarden:
      - **Geslaagd:** De afzender heeft de verificatiecontroles voor e-mail van afzenders (SPF of DKIM) doorgegeven.
      - **Mislukt:** de afzender heeft de verificatie van EOP-afzenders mislukt.
      - **Onbekend:** Het resultaat van deze controles is niet bekend.

   - **Beslissing ingesteld door**: Geeft aan wie heeft bepaald of de verzendende infrastructuur de gebruiker mag vervalsen:
       - **Spoof intelligence policy** (automatisch)
       - **Beheerder** (handmatig)

   - **Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met de vervalste gebruiker.

   - **Toegestaan om te vervalsen?**: De waarden die u hier ziet, zijn:
     - **Ja:** Berichten uit de combinatie van vervalste gebruikers- en verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.
     - **Nee:** Berichten uit de combinatie van vervalste gebruikers- en verzendende infrastructuur worden gemarkeerd als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**). Zie de volgende sectie voor meer informatie.

     - **Sommige gebruikers** **(alleen het** tabblad Domeinen): Een verzendende infrastructuur is een spoofing van meerdere gebruikers, waarbij sommige vervalste gebruikers zijn toegestaan en andere niet. Gebruik het **tabblad Gedetailleerd** om de specifieke adressen te bekijken.

6. Klik onder aan de pagina op **Opslaan.**

#### <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell gebruiken om vervalste afzenders te beheren

Gebruik de volgende syntaxis om toegestane en geblokkeerde afzenders weer te geven in spoof intelligence:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Dit voorbeeld retourneert gedetailleerde informatie over alle afzenders die gebruikers in uw domeinen mogen spoofen.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Zie [Get-PhishFilterPolicy (Get-PhishFilterPolicy)](/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

Als u toegestane en geblokkeerde afzenders wilt configureren in spoofinformatie, volgt u de volgende stappen:

1. Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de **cmdlet Get-PhishFilterPolicy** te schrijven naar een CSV-bestand door de volgende opdracht uit te voeren:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bewerk het CSV-bestand om de volgende waarden toe te voegen of te wijzigen:
   - **Afzender** (domein in de PTR-record of IP/24-adres van de bronserver)
   - **SpoofedUser:** Een van de volgende waarden:
     - Het e-mailadres van de interne gebruiker.
     - Het e-maildomein van de externe gebruiker.
     - Een lege waarde die aangeeft dat u alle vervalste berichten van de opgegeven afzender wilt blokkeren of **toestaan,** ongeacht het vervalste e-mailadres.
   - **AllowedToSpoof** (Ja of Nee)
   - **SpoofType** (intern of extern)

   Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de volgende `$UpdateSpoofedSenders` opdracht:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Gebruik de `$UpdateSpoofedSenders` variabele om het spoof intelligence-beleid te configureren door de volgende opdracht uit te voeren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Zie [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>Vervalste afzenders beheren in het inzicht in spoof intelligence

1. Ga in het & Compliancecentrum naar **Threat Management** \> **Dashboard.**

2. Zoek in **de rij** Inzichten naar een van de volgende items:

   - **Waarschijnlijk vervalste domeinen in** de afgelopen zeven dagen: Dit inzicht geeft aan dat spoof intelligence is ingeschakeld (deze is standaard ingeschakeld).
   - **Spoofbeveiliging inschakelen:** dit inzicht geeft aan dat spoofinformatie is uitgeschakeld en als u op het inzicht klikt, kunt u spoofinformatie inschakelen.

3. In het inzicht op het dashboard ziet u de volgende informatie:

   ![Schermafbeelding van inzicht in spoof intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft twee modi:

   - **Insight-modus:** als spoof intelligence is ingeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.
   - **Wat als de modus**: Als spoof intelligence is  uitgeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.

   Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, zijn onderverdeeld in twee categorieën: **Verdachte** domeinen en **Niet-verdachte domeinen.**

   - **Verdachte domeinen:**
     - **Spoof** met veel vertrouwen: op basis van de historische verzendingspatronen en de reputatiescore van de domeinen, zijn we ervan overtuigd dat de domeinen spoofing zijn en dat berichten uit deze domeinen waarschijnlijk schadelijk zijn.
     - **Matig vertrouwen spoof:** Op basis van historische verzendende patronen en de reputatiescore van de domeinen, zijn we er redelijk zeker van dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn. False positives zijn waarschijnlijker in deze categorie dan spoof met veel vertrouwen.
   - **Niet-verdachte domeinen:** het domein is mislukt expliciete e-mailverificatie [controleert SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)). Het domein is echter geslaagd voor onze impliciete e-mailverificatiecontroles[(samengestelde verificatie).](email-validation-and-authentication.md#composite-authentication) Hierdoor is er geen anti-spoofing actie ondernomen op het bericht.

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>Gedetailleerde informatie weergeven over verdachte en niet-gunstige domeinen

1. Klik op de informatie over spoofinformatie op **Verdachte domeinen** of **Niet-verdachte** domeinen om naar de pagina Inzicht in **spoofinformatie te** gaan. De **pagina Spoof Intelligence Insight** bevat de volgende informatie:

   - **Vervalst domein:** het domein van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients. Dit adres wordt ook wel het adres `5322.From` genoemd.
   - **Infrastructuur:** ook wel de _verzendende infrastructuur genoemd._ Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver. Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).
   - **Aantal berichten:** het aantal berichten van de verzendende infrastructuur naar uw organisatie dat het opgegeven vervalste domein bevat in de afgelopen 7 dagen.
   - **Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met het vervalste domein.
   - **Type spoof:** deze waarde is **Extern**.
   - **Toegestaan om te vervalsen?**: De waarden die u hier ziet, zijn:
     - **Ja:** Berichten uit de combinatie van het domein van de vervalste gebruiker en de verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.
     - **Nee:** Berichten uit de combinatie van het domein van de vervalste gebruiker en de verzendende infrastructuur worden gemarkeerd als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).

2. Selecteer een item in de lijst om details over het domein/verzendende infrastructuurpaar in een flyout weer te geven. De informatie omvat:
   - Waarom we dit hebben gesnapt.
   - Wat u moet doen.
   - Een domeinoverzicht.
   - WhoIs-gegevens over de afzender.
   - Soortgelijke berichten die we hebben gezien in uw tenant van dezelfde afzender.

   Hier kunt u er ook voor kiezen om het domein-/verzendende infrastructuurpaar toe te voegen of te verwijderen uit de **lijst Toegestane** afzender voor spoofing. Stel de schakelaar dienovereenkomstig in.

   ![Schermafbeelding van een domein in het deelvenster Informatie over spoofinformatie](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u spoofinformatie hebt geconfigureerd met afzenders die wel en niet mogen spoofen, gebruikt u een van de volgende stappen:

- Ga in het beveiligings- & compliancecentrum naar Beleid voor bedreigingsbeheer  \>  \> **Antispam** \>  \>  \>    uitvbreed spoofinformatiebeleid selecteer Mij afzenders laten zien die ik al heb bekeken, selecteer het tabblad Uw domeinen of Externe domeinen en controleer de waarde Toegestaan om te spoofen? voor de afzender.

- Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die wel en niet mogen spoofen:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- Voer in PowerShell de volgende opdracht uit om de lijst met alle vervalste afzenders te exporteren naar een CSV-bestand:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
