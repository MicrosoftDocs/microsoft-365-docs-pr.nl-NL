---
title: Spoofberichten configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over spoof intelligence in Exchange Online Protection (EOP), waar u specifieke vervalste afzenders kunt toestaan of blokkeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058874"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Spoof intelligence configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beschermd tegen spoofing door EOP. EOP gebruikt spoof intelligence als onderdeel van de algehele verdediging van uw organisatie tegen phishing. Zie Bescherming tegen spoofing in [EOP voor meer informatie.](anti-spoofing-protection.md)

Wanneer een afzender een e-mailadres vervalst, lijkt deze een gebruiker te zijn in een van de domeinen van uw organisatie of een gebruiker in een extern domein die e-mail naar uw organisatie verzendt. Aanvallers die afzenders spoofen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd. Maar er zijn scenario's waarin legitieme afzenders spoofing gebruiken. Bijvoorbeeld:

- Legitieme scenario's voor het vervalsen van interne domeinen:

  - Afzenders van derden gebruiken uw domein om bulkmail naar uw eigen werknemers te verzenden voor bedrijfspeilingen.
  - Een extern bedrijf genereert en verzendt namens u reclame- of productupdates.
  - Een assistent moet regelmatig e-mail verzenden voor een andere persoon binnen uw organisatie.
  - Met een interne toepassing worden e-mailmeldingen verzonden.

- Legitieme scenario's voor spoofing van externe domeinen:

  - De afzender staat op een adressenlijst (ook wel een discussielijst genoemd) en de adressenlijst geeft e-mail door van de oorspronkelijke afzender naar alle deelnemers op de adressenlijst.
  - Een extern bedrijf verzendt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-servicebedrijf).

Spoof intelligence, en met name het standaardbeleid voor spoof intelligence (en alleen spoof intelligence), helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet wordt meegesnnapt in EOP-spamfilters of externe e-mailsystemen, terwijl uw gebruikers worden beschermd tegen spam- of phishingaanvallen.

U kunt spoofinformatie beheren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan. Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u het spoof intelligence-beleid wilt wijzigen of spoofinformatie wilt in- of uitschakelen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot het spoof intelligence-beleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie Standaardinstellingen voor [anti-phishingbeleid](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)van EOP voor onze aanbevolen instellingen voor spoofinformatie.

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Het beveiligings- & compliancecentrum gebruiken om vervalste afzenders te beheren

> [!NOTE]
> Als u een Microsoft 365 Enterprise E5-abonnement hebt of afzonderlijk een Microsoft Defender voor Office 365-invoegabonnement hebt gekocht, kunt u ook afzenders beheren die uw domein spoofen via het inzicht in [Spoof Intelligence.](walkthrough-spoof-intelligence-insight.md)

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op ![ Pictogram Uitvvllen ](../../media/scc-expand-icon.png) om **spoofintelligentiebeleid uit te vouwen.**

   ![Het spoof intelligence-beleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Maak een van de volgende selecties:

   - **Nieuwe afzenders controleren**
   - **Laat mij afzenders zien die ik al heb bekeken**

4. Selecteer een van de volgende tabbladen in de fly-out Beslissen of deze **afzenders** uw gebruikers mogen spoofen:

   - **Uw domeinen:** afzenders die gebruikers spoofen in uw interne domeinen.
   - **Externe domeinen:** afzenders die gebruikers spoofen in externe domeinen.

5. Klik ![ op Pictogram ](../../media/scc-expand-icon.png) Uitv in de kolom **Toegestaan om te** vervalsen? Kies **Ja** om de vervalste afzender toe te staan of kies **Nee om** het bericht te markeren als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**). Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

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

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell gebruiken om vervalste afzenders te beheren

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

1. Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de **cmdlet Get-PhishFilterPolicy** te schrijven naar een CSV-bestand:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bewerk het CSV-bestand om de **waarden SpoofedUser** (e-mailadres) en **AllowedToSpoof** (Ja of Nee) toe te voegen of te wijzigen. Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de naam `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Gebruik de `$UpdateSpoofedSenders` variabele om het spoof intelligence-beleid te configureren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Zie [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Gebruik het Beveiligings- & compliancecentrum om spoofinformatie te configureren

De configuratieopties voor spoofinformatie worden beschreven in [spoofinstellingen in anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)

U kunt spoof intelligence-instellingen configureren in het standaard anti-phishingbeleid en ook in aangepast beleid. Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:

- [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md).

- [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Gebruik een van de volgende stappen om te controleren of u spoofinformatie hebt geconfigureerd met afzenders die wel en niet mogen spoofen en of u de instellingen voor spoof intelligence hebt geconfigureerd:

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

- Ga in het & Compliance center naar **Threat management** \> **Policy** \> **Anti-phishing** of **ATP anti-phishing** en ga naar een van de volgende stappen:  

  - Selecteer een beleid in de lijst. Controleer in het flyout dat wordt weergegeven de waarden in de **sectie Spoof.**
  - Klik **op Standaardbeleid.** Controleer in het flyout dat wordt weergegeven de waarden in de **sectie Spoof.**

- Vervang in Exchange Online PowerShell \<Name\> door Office365 AntiPhish Default of de naam van een aangepast beleid en voer de volgende opdracht uit om de instellingen te controleren:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andere manieren om spoofing en phishing te beheren

Wees zorgvuldig met spoofing en phishingbeveiliging. Hier zijn verwante manieren om te controleren of afzenders uw domein vervalsen en te voorkomen dat ze uw organisatie beschadigen:

- Controleer het **spoof-e-mailrapport.** U kunt dit rapport vaak gebruiken om vervalste afzenders weer te geven en te beheren. Zie Rapport [Spoofdetecties voor meer informatie.](view-email-security-reports.md#spoof-detections-report)

- Controleer de SPF-configuratie (Sender Policy Framework). Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

- Controleer de DKIM-configuratie (DomainKeys Identified Mail). U moet DKIM naast SPF en DMARC gebruiken om te voorkomen dat aanvallers berichten verzenden die eruit zien alsof ze afkomstig zijn van uw domein. Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop. Zie DKIM gebruiken om uitgaande e-mail te valideren die is verzonden vanuit uw [aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)voor meer informatie.

- Controleer uw DMARC-configuratie (Domain-based Message Authentication, Reporting, and Conformance). De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email. DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen. Zie [DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md)voor meer informatie.