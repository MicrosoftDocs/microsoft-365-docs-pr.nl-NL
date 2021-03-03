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
description: Beheerders kunnen meer informatie krijgen over spoof intelligence in Exchange Online Protection (EOP), waar u specifieke vervalste afzenders kunt toestaan of blokkeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 482978e93325344d897fcf907b026743fc393d47
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406638"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Spoof Intelligence configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beveiligd tegen spoofing door EOP. EOP gebruikt spoof intelligence als onderdeel van de totale verdediging van uw organisatie tegen phishing. Zie Beveiliging tegen [adresvervalsing in EOP voor meer informatie.](anti-spoofing-protection.md)

Wanneer een afzender een e-mailadres vervalst, lijkt dit een gebruiker in een van de domeinen van uw organisatie of een gebruiker in een extern domein die e-mail naar uw organisatie verzendt. Aanvallers die afzenders spoofen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd. Er zijn echter gevallen waarin legitieme afzenders spoofing gebruiken. Bijvoorbeeld:

- Legitieme scenario's voor het vervalsen van interne domeinen:

  - Externe afzenders gebruiken uw domein om bulkmail naar uw eigen werknemers te verzenden voor bedrijfspeilingen.
  - Een extern bedrijf genereert en verzendt namens u advertenties of productupdates.
  - Een assistent moet regelmatig e-mail verzenden voor iemand anders binnen uw organisatie.
  - Een interne toepassing verzendt e-mailmeldingen.

- Legitieme scenario's voor het vervalsen van externe domeinen:

  - De afzender maakt deel uit van een adressenlijst (ook wel een discussielijst genoemd) en met de adressenlijst wordt e-mail van de oorspronkelijke afzender verzonden naar alle deelnemers aan de adressenlijst.
  - Een extern bedrijf verzendt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-service-bedrijf).

Spoof intelligence, en met name het standaard(en alleen) spoof intelligence-beleid, helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet wordt op de hoogte gehouden van de EOP-spamfilters of externe e-mailsystemen, terwijl uw gebruikers worden beschermd tegen spam of phishing-aanvallen.

U kunt spoof intelligence beheren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan. Als u rechtstreeks naar de **anti-phishing-pagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen toegewezen krijgen in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u het spoof intelligence-beleid wilt wijzigen of spoof intelligence wilt in- of uitschakelen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot het spoof intelligence-beleid moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie Machtigingen [in Exchange Online voor meer informatie.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  **Opmerkingen**:

  - Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol  in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie voor onze aanbevolen instellingen voor spoof intelligence de standaardinstellingen [voor anti-phishingbeleid van EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Het beveiligings- & voor het beheren van vervalste afzenders

> [!NOTE]
> Als u een Microsoft 365 Enterprise E5-abonnement hebt of afzonderlijk een invoegabonnement op Microsoft Defender voor Office 365 hebt gekocht, kunt u ook afzenders beheren die uw domein via spoof [intelligence-inzichten vervalsten.](walkthrough-spoof-intelligence-insight.md)

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispaminstellingen** op ![ het pictogram Uitvbreken ](../../media/scc-expand-icon.png) om intelligence-beleid voor **adresvervalsing uit te vouwen.**

   ![Het spoof intelligence-beleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Maak een van de volgende opties:

   - **Nieuwe afzenders controleren**
   - **Afzenders tonen die ik al heb beoordeeld**

4. Selecteer een van de volgende tabbladen bij Bepalen of deze **afzenders** uw flyout voor gebruikers mogen spoofen:

   - **Uw domeinen:** afzenders adresseren gebruikers in uw interne domeinen.
   - **Externe domeinen:** afzenders adresseren gebruikers in externe domeinen.

5. Klik ![ op het pictogram ](../../media/scc-expand-icon.png) Uitviekken in **de kolom Toegestaan naar spoof?** Kies **Ja om** de vervalste afzender toe te staan of kies Nee **om** het bericht te markeren als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleidsregels (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).** Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

   ![Schermafbeelding van de flyout voor vervalste afzenders en of de afzender mag spoofen](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   De kolommen en waarden die u ziet, worden in de volgende lijst uitgelegd:

   - **Vervalste gebruiker:** het gebruikersaccount dat wordt vervalst. Dit is de afzender van het bericht in het Van-adres (ook wel het adres genoemd) dat `5322.From` wordt weergegeven in e-mail clients. De geldigheid van dit adres wordt niet gecontroleerd door SPF.

     - Op het **tabblad Uw** domeinen bevat de waarde één e-mailadres. Als de bron-e-mailserver meerdere gebruikersaccounts spooft, bevat deze meer dan **één adres.**

     - Op het **tabblad Externe** domeinen bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.

   - **Infrastructuur verzenden:** het domein dat is gevonden in een omgekeerde DNS-zoekactie (PTR-record) van het IP-adres van de bron-e-mailserver. Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).

     Zie een overzicht van de standaarden voor e-mailberichten voor meer informatie over berichtbronnen [en afzenders van berichten.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **# van berichten:** het aantal berichten van de verzendende infrastructuur naar uw organisatie dat de opgegeven vervalste afzender of afzenders in de afgelopen 30 dagen bevat.

   - **# van gebruikers klachten:** Klachten die zijn ingediend door uw gebruikers tegen deze afzender in de afgelopen 30 dagen. Klachten zijn meestal in de vorm van ongewenste e-mail naar Microsoft.

   - **Resultaat van verificatie:** een van de volgende waarden:
      - **Geslaagd:** de afzender heeft de e-mailverificatiecontroles voor afzenders (SPF of DKIM) doorgegeven.
      - **Mislukt:** de afzender kan niet worden gecontroleerd op de verificatie van de EOP-afzender.
      - **Onbekend:** Het resultaat van deze controles is niet bekend.

   - **Beslissing ingesteld door:** Geeft aan wie heeft vastgesteld of de verzendende infrastructuur de gebruiker mag spoofen:
       - **Spoof intelligence policy** (automatisch)
       - **Beheerder** (handmatig)

   - **Laatst gezien:** de laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met de vervalste gebruiker.

   - **Mag worden vervalst?** De waarden die u hier ziet, zijn:
     - **Ja:** berichten van de combinatie van vervalste gebruikers- en verzenden-infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.
     - **Nee:** berichten van de combinatie van vervalste gebruikers- en verzendende infrastructuur worden gemarkeerd als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleidsregels (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).** Zie de volgende sectie voor meer informatie.

     - **Sommige gebruikers** **(alleen** op het tabblad Domeinen): Een verzendende infrastructuur vervalst meerdere gebruikers, waarbij sommige vervalste gebruikers zijn toegestaan en andere niet. Gebruik het **tabblad Gedetailleerd** om de specifieke adressen te zien.

6. Klik onder aan de pagina op **Opslaan.**

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell gebruiken om vervalste afzenders te beheren

Gebruik de volgende syntaxis om toegestane en geblokkeerde afzenders in spoof intelligence weer te geven:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In dit voorbeeld wordt gedetailleerde informatie gegeven over alle afzenders die gebruikers in uw domeinen mogen spoofen.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Zie [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

Als u toegestane en geblokkeerde afzenders in spoof intelligence wilt configureren, gaat u als volgt te werk:

1. Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de cmdlet **Get-PhishFilterPolicy** naar een CSV-bestand te schrijven:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bewerk het CSV-bestand om de waarden **SpoofedUser** (e-mailadres) en **AllowedToSpoof** (Ja of Nee) toe te voegen of te wijzigen. Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de `$UpdateSpoofedSenders` naam:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Gebruik de variabele `$UpdateSpoofedSenders` om het spoof intelligence-beleid te configureren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Zie [Set-PhishFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)gedetailleerde syntaxis- en parameterinformatie.

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Het beveiligings- & gebruiken om spoof intelligence te configureren

De configuratieopties voor spoof intelligence worden beschreven in [spoof-instellingen in anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)

U kunt intelligence-instellingen voor spoofing configureren in het standaard anti-phishingbeleid en ook in aangepaste beleidsregels. Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:

- [Anti-phishingbeleid configureren in EOP.](configure-anti-phishing-policies-eop.md)

- [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of spoof intelligence is geconfigureerd met afzenders die wel en niet mogen spoofen, en of u de instellingen voor spoof intelligence hebt geconfigureerd, gebruikt u een van de volgende stappen:

- Ga in het & Compliancecentrum voor  beveiligingsbeleid naar Beleid voor adresvervalsingsbeleid tegen \>  \> **ongewenste e-mail.** Selecteer \>  \> **'Afzenders** \>    die ik al heb beoordeeld' op het tabblad Uw domeinen of Externe domeinen en controleer of de waarde Is toegestaan voor spoofing? voor de afzender.

- Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die wel en niet mogen spoofen:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- Voer in PowerShell de volgende opdracht uit om de lijst met alle vervalste afzenders naar een CSV-bestand te exporteren:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- Ga in het & Compliancecentrum  naar Risicobeheerbeleid \>  \> **anti-phishing** of **ATP anti-phishing** en ga op een van de volgende stappen te werk:  

  - Selecteer een beleid in de lijst. In de flyout die wordt weergegeven, controleert u de waarden in de **sectie Adresvervalsing.**
  - Klik **op Standaardbeleid.** In de flyout die wordt weergegeven, controleert u de waarden in de **sectie Adresvervalsing.**

- Vervang in Exchange Online PowerShell door \<Name\> Office 365 Antiphish Default of de naam van een aangepast beleid en voer de volgende opdracht uit om de instellingen te controleren:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andere manieren om spoofing en phishing te beheren

Wees op de beveiliging tegen spoofing en phishing op de goede weg. Hier zijn gerelateerde manieren om te controleren of afzenders uw domein hebben vervalst en om te voorkomen dat ze uw organisatie beschadigen:

- Controleer het **spoof-e-mailrapport.** U kunt dit rapport vaak gebruiken voor het weergeven en beheren van vervalste afzenders. Zie het rapport [Spoof-detecties voor meer informatie.](view-email-security-reports.md#spoof-detections-report)

- Controleer de SPF-configuratie (Sender Policy Framework). Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

- Controleer de configuratie van uw DKIM (DomainKeys Identified Mail). U moet DKIM naast SPF en DMARC gebruiken om te voorkomen dat aanvallers berichten verzenden die lijken alsof ze van uw domein komen. Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop. Zie DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw aangepaste [domein in Office 365 voor meer informatie.](use-dkim-to-validate-outbound-email.md)

- Controleer de configuratie van de op domein gebaseerde berichtverificatie, rapportage en naleving (DMARC). De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email. DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen. Zie DMARC gebruiken om [e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)voor meer informatie.
