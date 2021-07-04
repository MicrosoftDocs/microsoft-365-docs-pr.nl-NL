---
title: DLP-beleidsvoorwaarden, uitzonderingen en acties
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: meer informatie over dlp-beleidsvoorwaarden en -uitzonderingen
ms.openlocfilehash: e85f9c1fdc19e125ef790d14e4e42d2390145fdc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288345"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>DLP-beleidsvoorwaarden, uitzonderingen en acties

Voorwaarden en uitzonderingen in DLP-beleid identificeren gevoelige items waar het beleid op wordt toegepast. Acties definiëren wat er gebeurt als gevolg van een uitzonderingsvoorwaarde die wordt voldaan.

- Voorwaarden bepalen wat u moet opnemen
- Uitzonderingen definiëren wat u moet uitsluiten.
- Acties definiëren wat er gebeurt als gevolg van voorwaarde of uitzondering die wordt voldaan

De meeste voorwaarden en uitzonderingen hebben één eigenschap die een of meer waarden ondersteunt. Als het DLP-beleid bijvoorbeeld wordt toegepast op Exchange e-mailberichten, **is** de afzender vereist voor de afzender van het bericht. Sommige voorwaarden hebben twee eigenschappen. De berichtkop **A** bevat bijvoorbeeld een van deze woorden voorwaarde vereist een eigenschap om het veld met de berichtkop op te geven en een tweede eigenschap om de tekst op te geven die moet worden gevonden in het veld met de koptekst. Sommige voorwaarden of uitzonderingen hebben geen eigenschappen. De voorwaarde Bijlage is bijvoorbeeld **beveiligd met** een wachtwoord en zoekt alleen naar bijlagen in berichten die met een wachtwoord zijn beveiligd.

Acties vereisen meestal extra eigenschappen. Als de DLP-beleidsregel bijvoorbeeld een bericht omleiden, moet u opgeven waar het bericht naar wordt omgeleid.
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Voorwaarden en uitzonderingen voor DLP-beleid

In de tabellen in de volgende secties worden de voorwaarden en uitzonderingen beschreven die beschikbaar zijn in DLP.

- [Afzenders](#senders)
- [Geadresseerden](#recipients)
- [Berichtonderwerp of -bericht](#message-subject-or-body)
- [Bijlagen](#attachments)
- [Berichtkoppen](#message-headers)
- [Berichteigenschappen](#message-properties)

### <a name="senders"></a>Afzenders

<br>

****

|voorwaarde of uitzondering in DLP|voorwaarde-/uitzonderingsparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Afzender is|voorwaarde: *Van* <br/> uitzondering: *ExceptIfFrom*|Adressen|Berichten die worden verzonden door de opgegeven postvakken, e-mailgebruikers, e-mailcontactgroepen of Microsoft 365 groepen in de organisatie.|
|IP-adres van afzender is|voorwaarde: *SenderIPRanges*<br/> uitzondering: *ExceptIfSenderIPRanges*|IPAddressRanges|Berichten waarbij het IP-adres van de afzender overeenkomt met het opgegeven IP-adres of binnen het opgegeven IP-adresbereik vallen.|
|Afzenderadres bevat woorden|voorwaarde: *FromAddressContainsWords* <br/> uitzondering: *ExceptIfFromAddressContainsWords*|Woorden|Berichten met de opgegeven woorden in het e-mailadres van de afzender.|
|Adres van afzender komt overeen met patronen|voorwaarde: *FromAddressMatchesPatterns* <br/> uitzondering: *ExceptFromAddressMatchesPatterns*|Patronen|Berichten waarin het e-mailadres van de afzender tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies.|
|Domein van afzender is|voorwaarde: *SenderDomainIs* <br/> uitzondering: *ExceptIfSenderDomainIs*|DomainName|Berichten waarin het domein van het e-mailadres van de afzender overeenkomt met de opgegeven waarde. Als u afzenderdomeinen wilt  zoeken die het opgegeven domein bevatten (bijvoorbeeld een subdomein van een domein), gebruikt u de voorwaarde Afzenderadres *(FromAddressMatchesPatterns)* en geeft u het domein op met de syntaxis: ' \. domein \. com$'.|
|Afzenderbereik|voorwaarde: *FromScope* <br/> uitzondering: *ExceptIfFromScope*|UserScopeFrom|Berichten die worden verzonden door interne of externe afzenders.|
|De opgegeven eigenschappen van de afzender bevatten een van deze woorden|voorwaarde: *SenderADAttributeContainsWords* <br/> uitzondering: *ExceptIfSenderADAttributeContainsWords*|Eerste eigenschap: `ADAttribute` <p> Tweede eigenschap: `Words`|Berichten waarin het opgegeven Active Directory-kenmerk van de afzender een van de opgegeven woorden bevat.|
|De opgegeven eigenschappen van de afzender komen overeen met deze tekstpatronen|voorwaarde: *SenderADAttributeMatchesPatterns* <br/> uitzondering: *ExceptIfSenderADAttributeMatchesPatterns*|Eerste eigenschap: `ADAttribute` <p> Tweede eigenschap: `Patterns`|Berichten waarin het opgegeven Active Directory-kenmerk van de afzender tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies.|
|

### <a name="recipients"></a>Geadresseerden

<br>

****

|voorwaarde of uitzondering in DLP|voorwaarde-/uitzonderingsparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Ontvanger is|voorwaarde: *SentTo* <br/> uitzondering: *ExceptIfSentTo*|Adressen|Berichten waarbij een van de geadresseerden het opgegeven postvak, e-mailgebruiker of e-mailcontactpunt in de organisatie is. De geadresseerden kunnen zich in de **velden Aan,** **CC** of **BCC van** het bericht.|
|Domein van ontvanger is|voorwaarde: *RecipientDomainIs* <br/> uitzondering: *ExceptIfRecipientDomainIs*|DomainName|Berichten waarin het domein van het e-mailadres van de geadresseerde overeenkomt met de opgegeven waarde.|
|Adres van ontvanger bevat woorden|voorwaarde: *AnyOfRecipientAddressContainsWords* <br/> uitzondering: *ExceptIfAnyOfRecipientAddressContainsWords*|Woorden|Berichten met de opgegeven woorden in het e-mailadres van de geadresseerde. <br/>**Opmerking:** deze voorwaarde houdt geen rekening met berichten die naar adresadressen van geadresseerden worden verzonden. Het komt alleen overeen met berichten die naar het primaire e-mailadres van de geadresseerde worden verzonden.|
|Adres van ontvanger komt overeen met patronen|voorwaarde: *AnyOfRecipientAddressMatchesPatterns* <br/> uitzondering: *ExceptIfAnyOfRecipientAddressMatchesPatterns*|Patronen|Berichten waarin het e-mailadres van een geadresseerde tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies. <br/> **Opmerking:** deze voorwaarde houdt geen rekening met berichten die naar adresadressen van geadresseerden worden verzonden. Het komt alleen overeen met berichten die naar het primaire e-mailadres van de geadresseerde worden verzonden.|
|Verzonden naar lid van|voorwaarde: *SentToMemberOf* <br/> uitzondering: *ExceptIfSentToMemberOf*|Adressen|Berichten met geadresseerden die lid zijn van de opgegeven distributiegroep, beveiligingsgroep met e-mail of Microsoft 365 groep. De groep kan zich in de **velden Aan,** **CC** of **BCC van** het bericht.|
|

### <a name="message-subject-or-body"></a>Berichtonderwerp of -bericht

<br>

****

|voorwaarde of uitzondering in DLP|voorwaarde-/uitzonderingsparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Onderwerp bevat woorden of woordgroepen|voorwaarde: *SubjectContainsWords* <br/> uitzondering: *ExceptIf SubjectContainsWords*|Woorden|Berichten met de opgegeven woorden in het veld Onderwerp.|
|Onderwerp komt overeen met patronen|voorwaarde: *SubjectMatchesPatterns* <br/> uitzondering: *ExceptIf SubjectMatchesPatterns*|Patronen|Berichten waarin het veld Onderwerp tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies.|
|Inhoud bevat|voorwaarde: *ContentContainsSensitiveInformation* <br/> uitzondering *ExceptIfContentContainsSensitiveInformation*|SensitiveInformationTypes|Berichten of documenten die gevoelige informatie bevatten, zoals gedefinieerd door DLP-beleid (Data Loss Prevention).|
|Patroon van onderwerp of body|voorwaarde: *SubjectOrBodyMatchesPatterns* <br/> uitzondering: *ExceptIfSubjectOrBodyMatchesPatterns*|Patronen|Berichten waarin het onderwerpveld of de berichttekst tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies.|
|Onderwerp of lichaam bevat woorden|voorwaarde: *SubjectOrBodyContainsWords* <br/> uitzondering: *ExceptIfSubjectOrBodyContainsWords*|Woorden|Berichten met de opgegeven woorden in het onderwerpveld of de berichtinstelling|
|

### <a name="attachments"></a>Bijlagen

<br>

****

|voorwaarde of uitzondering in DLP|voorwaarde-/uitzonderingsparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Bijlage is met wachtwoord beveiligd|voorwaarde: *DocumentIsPasswordProtected* <br/> uitzondering: *ExceptIfDocumentIsPasswordProtected*|geen|Berichten waarin een bijlage met een wachtwoord is beveiligd (en dus niet kunnen worden gescand). Wachtwoorddetectie werkt alleen voor Office documenten, .zip bestanden en .7z-bestanden.|
|De bestandsextensie van bijlage is|voorwaarde: *ContentExtensionMatchesWords* <br/> uitzondering: *ExceptIfContentExtensionMatchesWords*|Woorden|Berichten waarin de bestandsextensie van een bijlage overeenkomt met een van de opgegeven woorden.|
|De inhoud van een e-mailbijlage kan niet worden gescand|voorwaarde: *DocumentIsUnsupported* <br/>uitzondering: *ExceptIf DocumentIsUnsupported*|n/a|Berichten waarin een bijlage niet inheems wordt herkend door Exchange Online.|
|De inhoud van een e-mailbijlage is niet volledig gescand|voorwaarde: *ProcessingLimitExceeded* <br/> uitzondering: *ExceptIfProcessingLimitExceeded*|n/a|Berichten waarin de regels-engine het scannen van de bijlagen niet kon voltooien. U kunt deze voorwaarde gebruiken om regels te maken die samenwerken om berichten te identificeren en te verwerken waarin de inhoud niet volledig kan worden gescand.|
|Documentnaam bevat woorden|voorwaarde: *DocumentNameMatchesWords* <br/> uitzondering: *ExceptIfDocumentNameMatchesWords*|Woorden|Berichten waarin de bestandsnaam van een bijlage overeenkomt met een van de opgegeven woorden.|
|Documentnaam komt overeen met patronen|voorwaarde: *DocumentNameMatchesPatterns* <br/> uitzondering: *ExceptIfDocumentNameMatchesPatterns*|Patronen|Berichten waarin de bestandsnaam van een bijlage tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies.|
|De eigenschap Document is|voorwaarde: *ContentPropertyContainsWords* <br/> uitzondering: *ExceptIfContentPropertyContainsWords*|Woorden|Berichten of documenten waarin de bestandsextensie van een bijlage overeenkomt met een van de opgegeven woorden.|
|De documentgrootte is gelijk aan of groter dan|voorwaarde: *DocumentSizeOver* <br/> uitzondering: *ExceptIfDocumentSizeOver*|Grootte|Berichten waarin een bijlage groter is dan of gelijk is aan de opgegeven waarde.|
|De inhoud van een bijlage bevat een van deze woorden|voorwaarde: *DocumentContainsWords* <br/> uitzondering: *ExceptIfDocumentContainsWords*|`Words`|Berichten waarin een bijlage de opgegeven woorden bevat.|
|Inhoud van bijlagen komt overeen met deze tekstpatronen|voorwaarde: *DocumentMatchesPatterns* <br/> uitzondering: *ExceptIfDocumentMatchesPatterns*|`Patterns`|Berichten waarin een bijlage tekstpatronen bevat die overeenkomen met de opgegeven reguliere expressies.|
|

### <a name="message-headers"></a>Berichtkoppen

<br>

****

|voorwaarde of uitzondering in DLP|voorwaarde-/uitzonderingsparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Koptekst bevat woorden of woordgroepen|voorwaarde: *HeaderContainsWords* <br/> uitzondering: *ExceptIfHeaderContainsWords*|Hashtabel|Berichten die het opgegeven veld met de koptekst bevatten en de waarde van dat veld bevat de opgegeven woorden.|
|Koptekst komt overeen met patronen|voorwaarde: *HeaderMatchesPatterns* <br/> uitzondering: *ExceptIfHeaderMatchesPatterns*|Hashtabel|Berichten die het opgegeven veld met de koptekst bevatten en de waarde van dat veld bevat de opgegeven reguliere expressies.|

### <a name="message-properties"></a>Berichteigenschappen

<br>

****

|voorwaarde of uitzondering in DLP|voorwaarde-/uitzonderingsparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Met belang|voorwaarde: *WithImportance* <br/> uitzondering: *ExceptIfWithImportance*|Belang|Berichten die zijn gemarkeerd met het opgegeven belangniveau.|
|Inhoudstekenset bevat woorden|voorwaarde: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*|Tekensets|Berichten met een van de opgegeven namen van tekensets.|
|Heeft afzender overschrijven|voorwaarde: *HasSenderOverride* <br/> uitzondering: *ExceptIfHasSenderOverride*|n/a|Berichten waarin de afzender ervoor heeft gekozen om een DLP-beleid (Data Loss Prevention) te overschrijven. Zie Meer informatie over preventie van gegevensverlies voor meer informatie over [DLP-beleid](./dlp-learn-about-dlp.md)|
|Berichtentype komt overeen|voorwaarde: *MessageTypeMatches* <br/> uitzondering: *ExceptIfMessageTypeMatches*|MessageType|Berichten van het opgegeven type.|
|De berichtgrootte is groter dan of gelijk aan|voorwaarde: *MessageSizeOver* <br/> uitzondering: *ExceptIfMessageSizeOver*|`Size`|Berichten waarbij de totale grootte (bericht plus bijlagen) groter is dan of gelijk is aan de opgegeven waarde. **Opmerking:** Limieten voor berichtgrootte voor postvakken worden geëvalueerd vóór de regels voor e-mailstroom. Een bericht dat te groot is voor een postvak, wordt geweigerd voordat een regel met deze voorwaarde kan reageren op het bericht.|
|

## <a name="actions-for-dlp-policies"></a>Acties voor DLP-beleid

In deze tabel worden de acties beschreven die beschikbaar zijn in DLP.

<br>

****

|actie in DLP|actieparameters in Microsoft 365 PowerShell|eigenschapstype|beschrijving|
|---|---|---|---|
|Koptekst instellen|SetHeader|Eerste eigenschap: *Naam van koptekst* </br> Tweede eigenschap: *Koptekstwaarde*|Met de parameter SetHeader wordt een actie opgegeven voor de DLP-regel die een veld met koptekst en waarde in de berichtkop toevoegt of wijzigt. Deze parameter gebruikt de syntaxis 'HeaderName:HeaderValue'. U kunt meerdere koptekstnaam- en waardeparen opgeven, gescheiden door komma's|
|Koptekst verwijderen|RemoveHeader|Eerste eigenschap: *MessageHeaderField*</br> Tweede eigenschap: *Tekenreeks*|Met de parameter RemoveHeader wordt een actie opgegeven voor de DLP-regel die een koptekstveld uit de berichtkop verwijdert. Deze parameter gebruikt de syntaxis 'HeaderName' of 'HeaderName:HeaderValue'. U kunt meerdere koptekstnamen of veldnamen en waardeparen opgeven, gescheiden door komma's|
|Het bericht omleiden naar specifieke gebruikers|*RedirectMessageTo*|Adressen|Hiermee wordt het bericht omgeleid naar de opgegeven geadresseerden. Het bericht wordt niet bezorgd bij de oorspronkelijke geadresseerden en er wordt geen melding verzonden naar de afzender of de oorspronkelijke geadresseerden.|
|Het bericht ter goedkeuring doorsturen naar de afzendermanager|Gemiddeld|Eerste eigenschap: *ModerateMessageByManager*</br> Tweede eigenschap: *Boolean*|De parameter Moderate geeft een actie op voor de DLP-regel die het e-mailbericht naar een moderator verzendt. Deze parameter gebruikt de syntaxis: @{ModerateMessageByManager = <$true \| $false>;|
|Het bericht ter goedkeuring doorsturen naar specifieke goedkeurders|Gemiddeld|Eerste eigenschap: *ModerateMessageByUser*</br>Tweede eigenschap: *Adressen*|De parameter Moderate geeft een actie op voor de DLP-regel die het e-mailbericht naar een moderator verzendt. Deze parameter gebruikt de syntaxis: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Geadresseerde toevoegen|AddRecipients|Eerste eigenschap: *Veld*</br>Tweede eigenschap: *Adressen*|Hiermee voegt u een of meer geadresseerden toe aan het veld Aan/CC/BCC van het bericht. Deze parameter gebruikt de syntaxis: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Manager van de afzender toevoegen als geadresseerde|AddRecipients|Eerste eigenschap: *AddedManagerAction*</br>Tweede eigenschap: *Veld*|Hiermee voegt u de afzendermanager toe aan het bericht als het opgegeven type geadresseerde (Aan, CC, BCC) of wordt het bericht omgeleid naar de manager van de afzender zonder de afzender of de geadresseerde op de hoogte te stellen. Deze actie werkt alleen als het kenmerk Manager van de afzender is gedefinieerd in Active Directory. Deze parameter gebruikt de syntaxis: @{AddManagerAsRecipientType = "<To \| CC \| BCC>"}|
Voorbereidend onderwerp|PrependSubject|Tekenreeks|Hiermee voegt u de opgegeven tekst toe aan het begin van het veld Onderwerp van het bericht. Overweeg een spatie of dubbele punt te gebruiken (:) als het laatste teken van de opgegeven tekst om deze te onderscheiden van de oorspronkelijke onderwerptekst.</br>Als u wilt voorkomen dat dezelfde tekenreeks wordt toegevoegd aan berichten die al de tekst in het onderwerp bevatten (bijvoorbeeld antwoorden), voegt u de uitzondering 'Het onderwerp bevat woorden' (ExceptIfSubjectContainsWords) toe aan de regel.|
|HTML-vrijwaring toepassen|ApplyHtmlDisclaimer|Eerste eigenschap: *Tekst*</br>Tweede eigenschap: *Locatie*</br>Derde eigenschap: *terugvalactie*|Hiermee wordt de opgegeven HTML-vrijwaring toegepast op de vereiste locatie van het bericht.</br>Deze parameter gebruikt de syntaxis: @{ Text = " " ; Locatie = <Append \| Prepend>; FallbackAction = <\| Negeren negeren negeren \|> }|
|Bescherming Office 365-berichtversleuteling en rechten verwijderen|RemoveRMSTemplate|n/a|Hiermee verwijdert Office 365 versleuteling die is toegepast op een e-mail|
|
