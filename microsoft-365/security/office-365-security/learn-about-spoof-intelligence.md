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
description: Beheerders kunnen informatie vinden over spoof Intelligence in Exchange Online Protection (EOP), waar u specifieke afzenders kunt toestaan of blokkeren.
ms.openlocfilehash: 86771397f0175d389a69c1008e0ac5471697afc5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199599"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Spoof informatie configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvakken van Exchange Online worden inkomende e-mailberichten automatisch beveiligd tegen spoofing door EOP vanaf oktober 2018. EOP maakt gebruik van spoof Intelligence als onderdeel van de algemene verdediging van uw organisatie tegen phishing. Zie [anti-spoofing beveiliging in EOP](anti-spoofing-protection.md)voor meer informatie.

Wanneer een afzender een e-mailadres vervalst, lijken ze een gebruiker in een van de domeinen van uw organisatie of een gebruiker in een extern domein die e-mail naar uw organisatie verzendt. Kwaadwillenden die afzenders vervalsen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd. Er zijn echter scenario's waarbij originele afzenders spoofing zijn. Bijvoorbeeld:

- Legitieme scenario's voor het spoofen van interne domeinen:

  - Afzenders van derden uw domein gebruiken om bulkmail te versturen naar uw eigen werknemers voor bedrijfs polls.
  - Een extern bedrijf genereert en stuurt namens u advertenties of productupdates.
  - Een assistent moet regelmatig e-mail verzenden voor een andere persoon binnen uw organisatie.
  - Een interne toepassing verzendt e-mail meldingen.

- Legitieme scenario's voor het vervalsen van externe domeinen:

  - De afzender bevindt zich in een adressenlijst (ook wel discussielijst genoemd), en de adressenlijst stuurt e-mail van de oorspronkelijke afzender door naar alle deelnemers aan de adressenlijst.
  - Een extern bedrijf verzendt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-servicebedrijf).

Spoof Intelligence en specifiek het standaardbeleid voor spoof informatie van spoofing helpt ervoor te zorgen dat de vervalste e-mail die door legitieme afzenders is verzonden, niet wordt weergegeven in EOP spamfilters of externe e-mail systemen, terwijl u uw gebruikers tegen spam of phishing-aanvallen beschermt.

U kunt spoof Intelligence beheren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan. Als u rechtstreeks naar de **anti malafide** pagina wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u het beleid voor spoof informatie wilt wijzigen of spoof Intelligence wilt in-of uitschakelen, moet u lid zijn van een van de volgende rollen groepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot het beleid voor spoof Intelligence moet u lid zijn van een van de volgende rollen groepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Voor de aanbevolen instellingen voor spoof Intelligence raadpleegt u [EOP standaard anti phishingfilter-beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Het nalevings centrum voor beveiliging & gebruiken om vervalste afzenders te beheren

> [!NOTE]
> Als u een Microsoft 365 Enterprise E5-abonnement hebt of een Office 365 Advanced Threat 365 Protection-uitbreiieve Office-invoegtoepassing hebt gekocht, kunt u ook afzenders beheren die uw domein spoofen via de website van [spoof Intelligence](walkthrough-spoof-intelligence-insight.md).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om het **spoof Intelligence-beleid**uit te vouwen.

   ![Het beleid voor spoof informatie selecteren](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Voer een van de volgende opties in:

   - **Nieuwe afzenders controleren**
   - **Laat afzenders zien die ik al heb herzien**

4. Selecteer een van de volgende tabbladen in het menu **bepalen of deze afzenders toestemming hebben om uw gebruikers flyout te vervalsen** dat wordt weergegeven:

   - **Uw domeinen**: afzenders van afzenders gebruikers in uw interne domeinen.
   - **Externe domeinen**: afzenders spoofing gebruikers in externe domeinen.

5. Klik op ![ het pictogram uitvouwen ](../../media/scc-expand-icon.png) in de kolom **toegestaan voor spoof?** . Kies **Ja** als u de vervalste afzender wilt toestaan of kies **Nee** om het bericht als vervalste te markeren. De actie wordt bestuurd door het standaard anti-phishingfilter of aangepast ATP anti-spam beleid (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**). Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).

   ![Schermafbeelding van de flyout vervalste afzenders en of de afzender toestemming heeft om spoof te geven](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   De kolommen en waarden die u ziet, worden uitgelegd in de volgende lijst:

   - **Vervalste gebruiker**: het gebruikersaccount waarvan wordt spoofing. Dit is de afzender van het bericht in het van `5322.From` -adres dat wordt weergegeven in e-mailclients. De geldigheid van dit adres is niet gecontroleerd op SPF.

     - Op het tabblad **uw domeinen** bevat de waarde één e-mailadres of als de bron-e-mailserver een spoofing heeft voor meerdere gebruikersaccounts, het bevat **meer dan één**e-mailadres.

     - Op het tabblad **externe domeinen** bevat de waarde het domein van de vervalste gebruiker, niet het volledige e-mailadres.

   - **Infrastructuur verzenden**: het domein dat is gevonden in een omgekeerde DNS-zoekopdracht (PTR-record) van het IP-adres van de bron-e-mailserver of het IP-adres als de bron geen PTR-record heeft.

     Zie [een overzicht van de standaarden voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over berichten bronnen en afzenders van berichten.

   - **# van berichten**: het aantal berichten van de verzendende infrastructuur naar uw organisatie die de opgegeven vervalste afzender of afzenders in de afgelopen 30 dagen bevat.

   - **# van de klachten van gebruikers**: klachten die door uw gebruikers zijn ingediend binnen de afgelopen 30 dagen. De klachten vormen meestal in de vorm van ongewenste faxberichten aan Microsoft.

   - **Verificatie resultaat**: een van de volgende waarden:

      - **Doorgegeven**: de afzender heeft doorsturen van e-mail verificatie gecontroleerd of e-mail verificatie gecontroleerd.
      - **Mislukt**: de afzender is niet gelukt verificatiecontroles voor EOP te verzenden.
      - **Onbekend**: het resultaat van deze controles is onbekend.

   - **Beslissings instelling**: geeft aan welke persoon is bepaald of de verzending van de gebruiker spoofing mag maken:

       - **Beleid voor spoof informatie** (automatisch)
       - **Beheerder** (handmatig)

   - **Laatst weergegeven**: de laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur die de vervalste gebruiker bevat.

   - **Toegestaan spoofing?**: de waarden die u hier ziet:

     - **Ja**: berichten van de combinatie van vervalste gebruikers en het verzenden van een infrastructuur zijn toegestaan en worden niet als vervalste e-mail verwerkt.

     - **Nee**: berichten van de combinatie van vervalste gebruikers en het verzenden van de infrastructuur zijn gemarkeerd als vervalste. De actie wordt bestuurd door het standaard anti-phishingfilter of aangepast ATP anti-spam beleid (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**). Zie de volgende sectie voor meer informatie.

     - **Sommige gebruikers** (alleen de tabbladen van**uw domein** ): een verzendende infrastructuur is een spoofing voor meerdere gebruikers, waarbij sommige vervalste gebruikers zijn toegestaan en andere niet. Gebruik het tabblad **gedetailleerd** om de specifieke adressen weer te geven.

6. Klik onder aan de pagina op **Opslaan**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell gebruiken voor het beheren van vervalste afzenders

Als u toegestane en geblokkeerde afzenders wilt weergeven in spoof Intelligence, gebruikt u de volgende syntaxis:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In het volgende voorbeeld wordt gedetailleerde informatie geretourneerd over alle afzenders die zijn toegestaan voor spoofing aan gebruikers in uw domeinen.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Zie [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

Voer de volgende stappen uit om toegestane en geblokkeerde afzenders te configureren in spoof Intelligence:

1. De huidige lijst met gedetecteerde vervalste afzenders vastleggen door de uitvoer van de **Get-PhishFilterPolicy** -cmdlet te schrijven naar een CSV-bestand:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Het CSV-bestand bewerken om de **SpoofedUser** (e-mailadres) en **AllowedToSpoof** (ja of Nee) toe te voegen of te wijzigen. Sla het bestand op, lees het bestand en sla de inhoud op als een variabele met de naam `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Gebruik de `$UpdateSpoofedSenders` variabele om het beleid voor spoof informatie te configureren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Zie [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>De beveiligings & voor compliance gebruiken om spoof intelligence te configureren

De configuratieopties voor spoof Intelligence worden beschreven in de [spoofberichten-instellingen in anti phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).

U kunt instellingen voor spoof Intelligence configureren in het standaard anti-phishingfilter en ook in aangepaste beleidsregels. Zie een van de volgende onderwerpen voor instructies op basis van uw abonnement:

- Een [anti-phishing beleid configureren in EOP](configure-anti-phishing-policies-eop.md).

- [Configureer een anti-phishingfilter van ATP in Microsoft 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een van de volgende stappen uit om te controleren of u de gebruikers van de spoof-informatie hebt geconfigureerd met afzenders die zijn toegestaan en die niet zijn toegestaan voor spoofing en dat u de instellingen voor de spoof Intelligence hebt geconfigureerd:

- Ga in het beveiligings & compliance naar het **beleid voor** het oplossen van beveiligingsfuncties het \> **Policy** \> beleid voor het beleid voor spoofing **-** ondersteuning en selecteer de optie Ik wil \> **Spoof intelligence policy** \> **al gecontroleerde afzenders** \> **Your Domains** **External Domains** **Allowed to spoof?**

- Voer in PowerShell de volgende opdrachten uit om de afzenders weer te geven die zijn toegestaan en die niet zijn toegestaan voor spoofing:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- In PowerShell voert u de volgende opdracht uit om de lijst met alle vervalste afzenders te exporteren naar een CSV-bestand:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- Ga op een van de volgende **manieren te werk** in het beveiligings & nalevings centrum \> **Policy** \> : **anti phishing** of **ATP anti phishing**en voer een van de volgende stappen uit:  

  - Selecteer een beleid in de lijst. Controleer in het vervolgmenu dat wordt weergegeven, de waarden in de sectie **spoof** .
  - Klik op **standaardbeleid**. Controleer in het vervolgmenu dat wordt weergegeven, de waarden in de sectie **spoof** .

- Vervang in Exchange Online PowerShell de \<Name\> optie door Office365 AntiPhish standaard of de naam van een aangepast beleid, en voer de volgende opdracht uit om de instellingen te controleren:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andere manieren om spoofing en phishing te beheren

Wees zeer voor spoofing en phishing bescherming. Hier zijn een paar manieren om spoofing van afzenders te controleren en om te voorkomen dat ze uw organisatie gevaarlijk kunnen maken:

- Controleer het **e-mail rapport voor spoofberichten**. U kunt dit rapport vaak gebruiken om vervalste afzenders te bekijken en te beheren. Zie voor meer informatie het [rapport spoofberichten detectie](view-email-security-reports.md#spoof-detections-report).

- Controleer de SPF-configuratie (Sender Policy Framework). Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

- Controleer de configuratie van de door DomainKeys geïdentificeerde E-mail (DKIM). U kunt ook DKIM en de DMARC gebruiken om te voorkomen dat hackers berichten verzenden die eruitzien als ze afkomstig zijn van uw domein. Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop. Zie voor meer informatie [dkim gebruiken voor het valideren van uitgaande e-mail verzonden vanaf uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md).

- Controleer de configuratie van berichtverificatie, rapportage en conformiteit van uw domein (DMARC). De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email. DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen. Zie voor meer informatie [het artikel DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md).
