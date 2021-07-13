---
title: De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Beheerders kunnen leren hoe ze het beleid voor geavanceerde bezorging in Exchange Online Protection (EOP) kunnen gebruiken om berichten te identificeren die niet moeten worden gefilterd in specifieke ondersteunde scenario's (phishingsimulaties van derden en berichten die worden bezorgd in postvakken van beveiligingsbewerkingen (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383448"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> De functie die in dit artikel wordt beschreven, is in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.

Als u uw organisatie standaard veilig wilt [houden,](secure-by-default.md)staat Exchange Online Protection (EOP) geen veilige lijsten of filtering bypass toe voor berichten die zijn geïdentificeerd als malware of phishing met een hoog vertrouwen. Er zijn echter specifieke scenario's waarvoor niet-gefilterde berichten moeten worden bezorgd. Bijvoorbeeld:

- **Phishingsimulaties** van derden: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.
- **Postvakken voor beveiligingsbewerkingen (SecOps)**: Speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te verzamelen en te analyseren (zowel goed als slecht).

U gebruikt het _geavanceerde bezorgingsbeleid_ in Microsoft 365 om te voorkomen dat deze berichten _in_ deze specifieke scenario's worden gefilterd. <sup>\*</sup> Het geavanceerde bezorgingsbeleid zorgt ervoor dat berichten in deze scenario's de volgende resultaten bereiken:

- Filters in EOP en Microsoft Defender voor Office 365 actie ondernemen op deze berichten.<sup>\*</sup>
- [Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) voor spam en phishing onderneemt geen actie op deze berichten.<sup>\*</sup>
- [Standaardsysteemwaarschuwingen](alerts.md) worden niet geactiveerd voor deze scenario's.
- [Air en clustering in Defender voor Office 365](office-365-air.md) negeert deze berichten.
- Specifiek voor phishingsimulaties van derden:
  - [Beheerdersinzendingen genereren](admin-submission.md) een automatisch antwoord met de melding dat het bericht deel uitmaakt van een phishingsimulatiecampagne en geen echte bedreiging is. Waarschuwingen en AIR worden niet geactiveerd.
  - [Safe Koppelingen in Defender voor Office 365](safe-links.md) worden de specifiek geïdentificeerde URL's in deze berichten niet geblokkeerd of tot ontploffing gebracht.
  - [Safe bijlagen in Defender voor Office 365](safe-attachments.md) worden bijlagen in deze berichten niet tot ontploffing brengen.

<sup>\*</sup> U kunt malwarefilters of ZAP voor malware niet omzeilen.

Berichten die worden geïdentificeerd door het geavanceerde bezorgingsbeleid zijn geen beveiligingsrisico's, dus de berichten worden gemarkeerd als systeem overschrijven. Beheerders kunnen deze systeem overschrijven en analyseren in de volgende ervaringen:

- [Threat Explorer/Real-time detecties in Defender voor Office 365 plan 2](threat-explorer.md)
- De [pagina E-mailentiteit in Threat Explorer/Realtime detecties](mdo-email-entity-page.md)
- Het [rapport Status van bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Advanced hunting in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Campagneweergaven](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>. Als u rechtstreeks naar de pagina **Geavanceerde bezorging wilt** gaan, opent u <https://security.microsoft.com/advanceddelivery> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u geconfigureerde instellingen wilt maken, wijzigen of verwijderen in het  geavanceerde bezorgingsbeleid, moet u lid zijn van  de rollengroep Beveiligingsbeheerder in de **Microsoft 365 Defender-portal** en lid zijn van de rollengroep Organisatiebeheer in **Exchange Online.**
  - Voor alleen-lezen toegang tot het geavanceerde bezorgingsbeleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.

  > [!NOTE]
  > Gebruikers toevoegen aan de bijbehorende Azure Active Directory functie geeft gebruikers de vereiste machtigingen in de Microsoft 365 Defender _portal_ en machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Gebruik de Microsoft 365 Defender portal om SecOps-postvakken te configureren in het geavanceerde bezorgingsbeleid

1. Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & pagina Regels \>  \> **bedreigingsbeleid** sectie Regels \>  \> **Geavanceerde bezorging**.

2. Controleer op **de pagina** Geavanceerde bezorging of het **tabblad SecOps-postvak** is geselecteerd en ga vervolgens op een van de volgende stappen te werk:
   - Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**
   - Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**

3. Voer in **het flyout SecOps-postvakken** bewerken dat wordt geopend een bestaand Exchange Online-postvak in dat u wilt aanwijzen als SecOps-postvak door een van de volgende stappen uit te voeren:
   - Klik in het vak, laat de lijst met postvakken oplossen en selecteer het postvak.
   - Klik in het vak om een id voor het postvak te typen (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) en selecteer het postvak (weergavenaam) in de resultaten.

     Herhaal deze stap zo vaak als nodig is. Distributiegroepen zijn niet toegestaan.

     Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

4. Klik op **Opslaan** wanneer u gereed bent.

De secops-postvakinzendingen die u hebt geconfigureerd, worden weergegeven op het **tabblad SecOps-postvak.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Gebruik de Microsoft 365 Defender portal om phishingsimulaties van derden te configureren in het beleid voor geavanceerde bezorging

1. Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & pagina Regels \>  \> **bedreigingsbeleid** sectie Regels \>  \> **Geavanceerde bezorging**.

2. Selecteer op **de pagina** Geavanceerde bezorging het **tabblad Phishingsimulatie** en ga vervolgens op een van de volgende stappen te werk:
   - Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**
   - Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**

3. Configureer de volgende instellingen in het flyout **phishingsimulatie** van derden bewerken dat wordt geopend:

   - **Domein** verzenden: Vouw deze instelling uit en voer ten minste één e-mailadresdomein in (bijvoorbeeld contoso.com) door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven. Herhaal deze stap zo vaak als nodig is. U kunt maximaal tien items toevoegen.
   - **IP verzenden:** Vouw deze instelling uit en voer ten minste één geldig IPv4-adres in door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven. Herhaal deze stap zo vaak als nodig is. U kunt maximaal tien items toevoegen. Geldige waarden zijn:
     - Enkel IP: bijvoorbeeld 192.168.1.1.
     - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.
     - CIDR IP: Bijvoorbeeld 192.168.0.1/25.
   - **Url's** voor simulaties om dit mogelijk te maken: Vouw deze instelling uit en voer desgewenst specifieke URL's in die deel uitmaken van uw phishingsimulatiecampagne die niet mogen worden geblokkeerd of gedetoneerd door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven. U kunt maximaal tien items toevoegen. Zie URL-syntaxis voor [de tenantlijst toestaan/blokkeren](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)voor de syntaxis van de URL.

   Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

4. Wanneer u klaar bent, gaat u op een van de volgende stappen te werk:
   - **Eerste keer:** Klik **op Toevoegen** en klik vervolgens op **Sluiten.**
   - **Bestaand bewerken:** Klik **op Opslaan** en klik vervolgens op **Sluiten.**

De phishingsimulatiegegevens van derden die u hebt geconfigureerd, worden weergegeven op het **tabblad Phishingsimulatie.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Extra scenario's waarvoor filteren moet worden omzeild

Naast de twee scenario's waar het geavanceerde bezorgingsbeleid u bij kan helpen, zijn er andere scenario's waarvoor het filteren mogelijk moet worden overgeslagen:

- **Filters van derden:** Als de MX-record  van uw domein niet naar Office 365 (berichten worden eerst ergens anders gerouteerd), is beveiliging standaard niet [](secure-by-default.md) *beschikbaar.* Als u bescherming wilt toevoegen, moet u Verbeterde filtering voor connectors (ook wel skip listing genoemd) *inschakelen.* Zie E-mailstroom beheren met [een externe cloudservice](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)met Exchange Online. Als u geen uitgebreide filtering voor connectors wilt gebruiken, gebruikt u regels voor e-mailstroom (ook wel transportregels genoemd) om Microsoft-filtering te omzeilen voor berichten die al zijn geëvalueerd door filtering van derden. Zie E-mailstroomregels gebruiken om de SCL in berichten [in te stellen voor meer informatie.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **False positives under review**: U wilt mogelijk bepaalde berichten die nog steeds door Microsoft worden geanalyseerd [via](admin-submission.md) beheerdersinzendingen tijdelijk toestaan om bekende goede berichten te melden die ten onrechte als slecht worden gemarkeerd voor Microsoft (false positives). Net als bij alle **** overschrijvingen wordt ten zeerste aanbevolen dat deze vergoedingen tijdelijk zijn.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online PowerShell-procedures voor SecOps-postvakken in het beleid voor geavanceerde bezorging

In Exchange Online PowerShell zijn de basiselementen van SecOps-postvakken in het geavanceerde bezorgingsbeleid:

- **Het SecOps-beleid overschrijven:** beheerd door **\* de cmdlets -SecOpsOverridePolicy.**
- **De secops-overschrijvenregel:** wordt beheerd door **\* de cmdlets -SecOpsOverrideRuleRule.**

Dit gedrag heeft de volgende resultaten:

- U maakt eerst het beleid en vervolgens maakt u de regel die het beleid aangeeft waar de regel op van toepassing is.
- Wanneer u een beleid uit PowerShell verwijdert, wordt de bijbehorende regel ook verwijderd.
- Wanneer u een regel uit PowerShell verwijdert, wordt het bijbehorende beleid niet verwijderd. U moet het bijbehorende beleid handmatig verwijderen.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>PowerShell gebruiken om SecOps-postvakken te configureren

Het configureren van een SecOps-postvak in het geavanceerde bezorgingsbeleid in PowerShell is een proces in twee stappen:

1. Het secops-overschrijvenbeleid maken.
2. Maak de SecOps-overschrijvenregel die het beleid aangeeft waar de regel op van toepassing is.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Stap 1: PowerShell gebruiken om het secops-overschrijvenbeleid te maken

Als u het secops-overschrijvenbeleid wilt maken, gebruikt u de volgende syntaxis:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Opmerking:** Ongeacht de naam die u opgeeft, is de naam van het beleid SecOpsOverridePolicy, dus u kunt die waarde net zo goed gebruiken.

In dit voorbeeld wordt het secops-postvakbeleid gemaakt.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

Zie [New-SecOpsOverridePolicy (Nieuw-SecOpsOverridePolicy)](/powershell/module/exchange/new-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Stap 2: PowerShell gebruiken om de secops-overschrijvenregel te maken

In dit voorbeeld wordt de regel SecOps-postvak gemaakt met de opgegeven instellingen.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Opmerking:****Ongeacht de waarde Naam die u opgeeft, is de regelnaam SecOpsOverrideRule waar een unieke \<GUID\> \<GUID\> GUID-waarde is (bijvoorbeeld 6fed4b63-3563-495d-a481-b24a311f8329).

Zie [New-SecOpsOverrideRule voor](/powershell/module/exchange/new-secopsoverriderule)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-the-secops-override-policy"></a>PowerShell gebruiken om het beleid voor secops-overschrijven weer te geven

Dit voorbeeld retourneert gedetailleerde informatie over het ene en alleen secops-postvakbeleid.

```powershell
Get-SecOpsOverridePolicy
```

Zie [Get-SecOpsOverridePolicy (Get-SecOpsOverridePolicy)](/powershell/module/exchange/get-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-secops-override-rules"></a>PowerShell gebruiken om regels voor secops-overschrijven weer te geven

Dit voorbeeld retourneert gedetailleerde informatie over secops-regels die regels overschrijven.

```powershell
Get-SecOpsOverrideRule
```

Hoewel de vorige opdracht slechts één regel moet retourneren, kunnen regels die in behandeling zijn voor verwijdering, ook worden opgenomen in de resultaten.

In dit voorbeeld worden de geldige regel (één) en eventuele ongeldige regels geïdentificeerd.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

Nadat u de ongeldige regels hebt opgegeven, kunt u deze verwijderen met de cmdlet **Remove-SecOpsOverrideRule,** zoals [verderop in dit artikel wordt beschreven.](#use-powershell-to-remove-secops-override-rules)

Zie [Get-SecOpsOverrideRule (Get-SecOpsOverrideRule)](/powershell/module/exchange/get-secopsoverriderule) voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>PowerShell gebruiken om het secops-overschrijvenbeleid te wijzigen

Gebruik de volgende syntaxis om het secops-overschrijvenbeleid te wijzigen:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

In dit voorbeeld worden secops2@contoso.com toegevoegd aan het secops-overschrijvenbeleid.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Opmerking:** Als er een bijbehorende, geldige SecOps-overschrijvenregel bestaat, worden de e-mailadressen in de regel ook bijgewerkt.

Zie [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>PowerShell gebruiken om een SecOps-overschrijvenregel te wijzigen

De **cmdlet Set-SecOpsOverrideRule** wijzigt de e-mailadressen in de secops-overschrijvenregel niet. Als u de e-mailadressen in de secops-overschrijvenregel wilt wijzigen, gebruikt u de cmdlet **Set-SecOpsOverridePolicy.**

Zie [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>PowerShell gebruiken om het SecOps-overschrijvenbeleid te verwijderen

In dit voorbeeld worden het secopspostvakbeleid en de bijbehorende regel verwijderd.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Zie [Remove-SecOpsOverridePolicy (Verwijderen-SecOpsOverridePolicy)](/powershell/module/exchange/remove-secopsoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-secops-override-rules"></a>PowerShell gebruiken om SecOps-regels te verwijderen

Als u een secops-overschrijvenregel wilt verwijderen, gebruikt u de volgende syntaxis:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

In dit voorbeeld wordt de opgegeven SecOps-overschrijvenregel verwijderd.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Zie [Remove-SecOpsOverrideRule voor](/powershell/module/exchange/remove-secopsoverriderule)gedetailleerde syntaxis- en parametergegevens.

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online PowerShell-procedures voor phishingsimulaties van derden in het beleid voor geavanceerde bezorging

In Exchange Online PowerShell zijn de basiselementen van phishingsimulaties van derden in het geavanceerde bezorgingsbeleid:

- **De phishingsimulatie overschrijven het beleid:** gecontroleerd door **\* de cmdlets -PhishSimOverridePolicy.**
- **De phishingsimulatie overschrijven regel:** Gecontroleerd door **\* de cmdlets -PhishSimOverrideRule.**

Dit gedrag heeft de volgende resultaten:

- U maakt eerst het beleid en vervolgens maakt u de regel die het beleid aangeeft waar de regel op van toepassing is.
- U wijzigt de instellingen in het beleid en de regel afzonderlijk.
- Wanneer u een beleid uit PowerShell verwijdert, wordt de bijbehorende regel ook verwijderd.
- Wanneer u een regel uit PowerShell verwijdert, wordt het bijbehorende beleid niet verwijderd. U moet het bijbehorende beleid handmatig verwijderen.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>PowerShell gebruiken om phishingsimulaties van derden te configureren

Het configureren van een phishingsimulatie van derden in het beleid voor geavanceerde bezorging in PowerShell is een proces in twee stappen:

1. Maak het beleid voor phishingsimulatie.
2. Maak de overschrijvende regel voor phishingsimulatie die het beleid aangeeft waar de regel op van toepassing is.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Stap 1: PowerShell gebruiken om het beleid voor phishingsimulatie te overschrijven

In dit voorbeeld wordt het beleid voor phishingsimulatie overschrijven.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Opmerking:** Ongeacht de naam die u opgeeft, is de naam van het beleid PhishSimOverridePolicy, dus u kunt deze waarde net zo goed gebruiken.

Zie [New-PhishSimOverridePolicy (Nieuw-PhishSimOverridePolicy)](/powershell/module/exchange/new-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Stap 2: PowerShell gebruiken om de regel voor phishingsimulatie te maken

Gebruik de volgende syntaxis:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Ongeacht de waarde Naam die u opgeeft, is de regelnaam PhishSimOverrideRule waar een unieke \<GUID\> \<GUID\> GUID-waarde is (bijvoorbeeld a0eae53e-d755-4a42-9320-b9c6b55c5011).

Een geldige IP-adresinvoer is een van de volgende waarden:

- Enkel IP: bijvoorbeeld 192.168.1.1.
- IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.
- CIDR IP: Bijvoorbeeld 192.168.0.1/25.

In dit voorbeeld wordt de regel voor phishingsimulatie met de opgegeven instellingen overschreven.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Zie [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>PowerShell gebruiken om het beleid voor phishingsimulaties te bekijken

Dit voorbeeld retourneert gedetailleerde informatie over de enige phishingsimulatie die beleid overschrijven.

```powershell
Get-PhishSimOverridePolicy
```

Zie [Get-PhishSimOverridePolicy (Get-PhishSimOverridePolicy)](/powershell/module/exchange/get-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>PowerShell gebruiken om regels voor phishingsimulatie te bekijken

Dit voorbeeld retourneert gedetailleerde informatie over regels voor phishingsimulatie.

```powershell
Get-PhishSimOverrideRule
```

Hoewel de vorige opdracht slechts één regel moet retourneren, kunnen regels die in behandeling zijn voor verwijdering, ook worden opgenomen in de resultaten.

In dit voorbeeld worden de geldige regel (één) en eventuele ongeldige regels geïdentificeerd.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

Nadat u de ongeldige regels hebt opgegeven, kunt u deze verwijderen met de **cmdlet Remove-PhisSimOverrideRule,** [zoals verder wordt beschreven in dit artikel.](#use-powershell-to-remove-phishing-simulation-override-rules)

Zie [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>PowerShell gebruiken om het beleid voor phishingsimulaties te wijzigen

Als u het beleid voor phishingsimulaties wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt het beleid voor phishingsimulatie uitgeschakeld.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Zie [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>PowerShell gebruiken om een phishingsimulatieregel te wijzigen

Als u de regel voor phishingsimulaties wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

In dit voorbeeld wijzigt u de opgegeven phishingsimulatieregel met de volgende instellingen:

- Voeg de domeininvoer blueyonderairlines.com.
- Verwijder de IP-adresinvoer 192.168.1.55.

Houd er rekening mee dat deze wijzigingen geen invloed hebben op bestaande vermeldingen.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Zie [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>PowerShell gebruiken om een beleid voor phishingsimulatie te verwijderen

In dit voorbeeld worden het phishingsimulatiebeleid en de bijbehorende regel verwijderd.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Zie [Remove-PhishSimOverridePolicy (Verwijderen-PhishSimOverridePolicy)](/powershell/module/exchange/remove-phishsimoverridepolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>PowerShell gebruiken om regels voor phishingsimulatie te verwijderen

Als u een phishingsimulatieregel wilt verwijderen, gebruikt u de volgende syntaxis:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

In dit voorbeeld wordt de opgegeven regel voor phishingsimulatie verwijderd.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Zie [Remove-PhishSimOverrideRule voor](/powershell/module/exchange/remove-phishsimoverriderule)gedetailleerde syntaxis- en parametergegevens.
