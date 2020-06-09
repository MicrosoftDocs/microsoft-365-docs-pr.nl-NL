---
title: Spoofberichten configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over spoofinformatie in Exchange Online Protection (EOP), waar u specifieke vervalste afzenders toestaan of blokkeren.
ms.openlocfilehash: fe1e8f8a2e9f0cc792dc802ea5c7362af00687ae
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613238"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Spoofinformatie configureren in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken worden binnenkomende e-mailberichten vanaf oktober 2018 automatisch beschermd tegen spoofing door EOP. EOP maakt gebruik van spoofinformatie als onderdeel van de algehele verdediging van uw organisatie tegen phishing. Zie [Anti-spoofing-bescherming in EOP](anti-spoofing-protection.md)voor meer informatie.

Wanneer een afzender een e-mailadres vervalst, lijkt deze gebruiker te zijn in een van de domeinen van uw organisatie of een gebruiker in een extern domein dat e-mail naar uw organisatie verzendt. Aanvallers die afzenders spoofen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd. Maar er zijn scenario's waar legitieme afzenders spoofing zijn. Bijvoorbeeld:

- Legitieme scenario's voor spoofing interne domeinen:

  - Externe afzenders gebruiken uw domein om bulkmail naar uw eigen werknemers te sturen voor bedrijfspeilingen.

  - Een extern bedrijf genereert en verzendt namens u advertentie- of productupdates.

  - Een assistent moet regelmatig e-mail verzenden voor een andere persoon binnen uw organisatie.

  - Een interne toepassing stuurt e-mailmeldingen.

- Legitieme scenario's voor spoofing externe domeinen:

  - De afzender staat op een mailinglijst (ook wel een discussielijst genoemd) en de mailinglijst stuurt e-mail van de oorspronkelijke afzender door naar alle deelnemers op de mailinglijst.

  - Een extern bedrijf stuurt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-service bedrijf).

Spoofinformatie, en met name het standaard (en alleen) spoofinformatiebeleid, helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders wordt verzonden, niet verstrikt raakt in EOP-spamfilters of externe e-mailsystemen, terwijl uw gebruikers worden beschermd tegen spam of phishing-aanvallen.

U spoofinformatie beheren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan. Als u rechtstreeks naar de **anti-phishingpagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u het spoofinformatiebeleid wilt wijzigen of spoofinformatie wilt inschakelen of uitschakelen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot het spoofinformatiebeleid moet u lid zijn van de rolgroep **Security Reader.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Zie [EOP standaard anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor spoofinformatie.

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Gebruik het Security & Compliance Center om vervalste afzenders te beheren

> [!NOTE]
> Als u een Microsoft 365 Enterprise E5-abonnement hebt of afzonderlijk een Office 365 Advanced Threat Protection (Office 365 ATP)-add-on hebt gekocht, u ook afzenders beheren die uw domein spoofen via het [inzicht in Spoof Intelligence.](walkthrough-spoof-intelligence-insight.md)

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om het **informatiebeleid voor spoofen**uit te vouwen.

   ![Het spoofintelligentiebeleid selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Maak een van de volgende selecties:

   - **Nieuwe afzenders bekijken**
   - **Stuurprogramma's laten zien die ik al heb beoordeeld**

4. Selecteer in **de beslissing of deze afzenders de** flyout van uw gebruikers mogen spoofen die wordt weergegeven, een van de volgende tabbladen:

   - **Uw domeinen:** afzenders spoofen gebruikers in uw interne domeinen.
   - **Externe domeinen**: Afzenders spoofing gebruikers in externe domeinen.

5. Klik ![ op Pictogram Uitvouwen ](../../media/scc-expand-icon.png) in de kolom Toegestaan **spoofen?** Kies **Ja** om de vervalste afzender toe te staan of kies **Nee** om het bericht als vervalst te markeren. De actie wordt beheerd door het standaard anti-phishingbeleid of het aangepaste ATP-antiphishingbeleid (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).** Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

   ![Schermafbeelding van de flyout van de vervalste afzenders en of de afzender mag spoofen](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   De kolommen en waarden die u ziet, worden uitgelegd in de volgende lijst:

   - **Vervalste gebruiker:** het gebruikersaccount dat wordt vervalt. Dit is de afzender van het bericht in het adres Van (ook wel het `5322.From` adres genoemd) dat wordt weergegeven in e-mailclients. De geldigheid van dit adres wordt niet gecontroleerd door SPF.

     - Op het tabblad **Uw domeinen** bevat de waarde één e-mailadres of als de brone-mailserver meerdere gebruikersaccounts vervalt, bevat deze **meer dan één**.

     - Op het tabblad **Externe domeinen** bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.

   - **Infrastructuur verzenden:** het domein dat wordt gevonden in een reverse DNS-lookup (PTR-record) van het IP-adres van de brone-mailserver of het IP-adres als de bron geen PTR-record heeft.

     Zie Een overzicht van de normen [voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichtbronnen en afzenders van berichten.

   - **aantal berichten**: het aantal berichten uit de verzendinfrastructuur naar uw organisatie dat de opgegeven vervalste afzender of afzenders bevat in de afgelopen 30 dagen.

   - **aantal klachten van gebruikers**: Klachten die door uw gebruikers tegen deze afzender in de afgelopen 30 dagen zijn ingediend. Klachten zijn meestal in de vorm van ongewenste inzendingen bij Microsoft.

   - **Verificatieresultaat**: een van de volgende waarden:

      - **Geslaagd**: De afzender geslaagd afzender e-mail authenticatie controles (SPF of DKIM).
      - **Mislukt:** de verificatiecontroles van de EOP-afzender is mislukt.
      - **Onbekend**: Het resultaat van deze controles is niet bekend.

   - **Besluit ingesteld door**: Geeft aan wie heeft bepaald of de verzendende infrastructuur de gebruiker mag spoofen:

       - **Spoofintelligentiebeleid** (automatisch)
       - **Beheerder** (handleiding)

   - **Laatst gezien**: De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur die de vervalste gebruiker bevat.

   - **Toegestaan om spoof?**: De waarden die je hier ziet zijn:

     - **Ja:** Berichten van de combinatie van vervalste gebruiker en verzendende infrastructuur zijn toegestaan en niet behandeld als vervalste e-mail.

     - **Nee:** Berichten van de combinatie van vervalste gebruiker en verzendende infrastructuur worden gemarkeerd als vervalst. De actie wordt beheerd door het standaard anti-phishingbeleid of het aangepaste ATP-antiphishingbeleid (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).** Zie de volgende sectie voor meer informatie.

     - **Sommige gebruikers** (alleen het tabblad**Uw domeinen):** een verzendende infrastructuur vervalst meerdere gebruikers, waarbij sommige spoofed gebruikers zijn toegestaan en andere niet. Gebruik het tabblad **Gedetailleerd** om de specifieke adressen te bekijken.

6. Klik onder aan de pagina op **Opslaan**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell gebruiken om vervalste afzenders te beheren

Als u toegestane en geblokkeerde afzenders in spoofintelligentie wilt bekijken, gebruikt u de volgende syntaxis:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In dit voorbeeld wordt gedetailleerde informatie geretourneerd over alle afzenders die gebruikers in uw domeinen mogen spoofen.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Zie [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie .

Voer de volgende stappen uit om toegestane en geblokkeerde afzenders in spoofinformatie te configureren:

1. Leg de huidige lijst met gedetecteerde vervalste afzenders vast door de uitvoer van de cmdlet **Get-PhishFilterPolicy** in een CSV-bestand te schrijven:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bewerk het CSV-bestand om de waarden **SpoofedUser** (e-mailadres) en **AllowedToSpoof** (Ja of Nee) toe te voegen of te wijzigen. Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de `$UpdateSpoofedSenders` naam:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Gebruik de `$UpdateSpoofedSenders` variabele om het spoofintelligentiebeleid te configureren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Zie [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens .

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Gebruik het Security & Compliance Center om spoofinformatie te configureren

De configuratieopties voor spoofinformatie worden beschreven in [spoofinstellingen in anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)

U instellingen voor spoofinformatie configureren in het standaardbeleid voor antiphishing en ook in aangepast beleid. Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:

- [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md).

- [Atp-beleid voor antiphishing configureren in Microsoft 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u spoofinformatie hebt geconfigureerd met afzenders die wel en niet mogen spoofen en of u de instellingen voor spoofinformatie hebt geconfigureerd, voert u een van de volgende stappen uit:

- Ga in het Security & Compliance Center naar Het beleid voor **bedreigingsbeheer** \> **Policy** \> **antispam** \> uit te breiden **Spooftellige intelligentie beleid** selecteer \> **Stuurprogramma's die ik al heb beoordeeld** selecteer het tabblad Uw \> **domeinen** of externe domeinen, en controleer de waarde toegestaan om te **spoofen?** **Allowed to spoof?**

- Voer in PowerShell de volgende opdrachten uit om de afzenders te bekijken die wel en niet mogen spoofen:

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

- Ga in het Security & Compliance Center naar **Threat Management** \> **Policy** \> **Anti-phishing** of **ATP anti-phishing**en doe een van de volgende stappen:  

  - Selecteer een beleid in de lijst. Controleer in de flyout die wordt weergegeven de waarden in de sectie **Spoof.**
  - Klik **op Standaardbeleid**. Controleer in de flyout die wordt weergegeven de waarden in de sectie **Spoof.**

- Vervang in Exchange Online PowerShell \<Name\> door Office365 AntiPhish Default of de naam van een aangepast beleid en voer de volgende opdracht uit om de instellingen te verifiëren:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andere manieren om spoofing en phishing te beheren

Wees ijverig over spoofing en bescherming tegen phishing. Hier volgen gerelateerde manieren om te controleren of afzenders uw domein spoofen en te voorkomen dat ze uw organisatie beschadigen:

- Controleer het **Spoof-e-mailrapport**. U dit rapport vaak gebruiken om vervalste afzenders te bekijken en te beheren. Zie Rapport [Spoofdetecties](view-email-security-reports.md#spoof-detections-report)voor informatie .

- Controleer de SPF-configuratie (Sender Policy Framework). Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

- Controleer uw DomeinKeys Identified Mail (DKIM) configuratie. U moet DKIM naast SPF en DMARC gebruiken om te voorkomen dat aanvallers berichten verzenden die eruit zien alsof ze uit uw domein komen. Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop. Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Office 365 is verzonden, te valideren](use-dkim-to-validate-outbound-email.md)voor informatie.

- Controleer uw DMARC-configuratie (Domain-based Message Authentication, Reporting, and Conformance) .Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration. De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email. DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen. Zie [DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md)voor informatie.
