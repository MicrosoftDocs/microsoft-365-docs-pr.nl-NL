---
title: Hoe Office 365 het Adres Van valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 'Om phishing te voorkomen, vereisen Office 365 en Outlook.com nu RFC-compliance voor From: adressen.'
ms.openlocfilehash: 6459faa22f29017568747b84bbd2935aad6763d1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805694"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Hoe Office 365 het Adres Van valideert om phishing te voorkomen

Office 365 en Outlook.com e-mailaccounts ontvangen een steeds groter aantal phishing-aanvallen. Een techniek die phishers gebruiken is het verzenden van berichten die waarden hebben voor het Adres dat niet voldoet aan [RFC 5322.](https://tools.ietf.org/html/rfc5322) Het adres Van: wordt ook wel de 5322.From adres genoemd. Om dit soort phishing te voorkomen, vereisen Office 365 en Outlook.com berichten die door de service zijn ontvangen om een RFC-compatibel Met: adres zoals beschreven in dit artikel op te nemen.

> [!NOTE]
> De informatie in dit artikel vereist dat u een basiskennis hebt van het algemene formaat van e-mailadressen. Zie Voor meer informatie [rfc 5322](https://tools.ietf.org/html/rfc5322) (met name de punten 3.2.3, 3.4 en 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321)en [RFC 3696](https://tools.ietf.org/html/rfc3696). Dit artikel gaat over beleidshandhaving voor de 5322.From adres. Dit artikel gaat niet over de 5321.MailFrom adres.

Helaas zijn er nog enkele verouderde e-mailservers op het internet die nog steeds "legitieme" e-mailberichten verzenden die een ontbrekende of misvormde Van: adres hebben. Als u regelmatig e-mail ontvangt van organisaties die deze verouderde systemen gebruiken, moedigt u deze organisaties aan om hun e-mailservers bij te werken om te voldoen aan moderne beveiligingsnormen.

Microsoft zal op 9 november 2017 beginnen met de uitrol van de handhaving van het beleid dat in dit artikel wordt beschreven.

## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Hoe Office 365 het gebruik van een geldige From: adres afdwingt om phishing-aanvallen te voorkomen

Office 365 voert wijzigingen aan in de manier waarop het het gebruik van het From: adres afdwingt in berichten die het ontvangt om u beter te beschermen tegen phishing-aanvallen. In dit artikel:

- [Alle berichten moeten een geldig Vanaf: adres bevatten](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)

- [Indeling van het Adres Van als u geen weergavenaam opneemt](how-office-365-validates-the-from-address.md#FormatNoDisplayName)

- [Indeling van het Adres Van: als u een weergavenaam opneemt](how-office-365-validates-the-from-address.md#FormatDisplayName)

- [Aanvullende voorbeelden van geldig en ongeldig Vanaf: adressen](how-office-365-validates-the-from-address.md#Examples)

- [Automatische antwoorden op uw aangepaste domein onderdrukken zonder het beleid Van:](how-office-365-validates-the-from-address.md#SuppressAutoReply)

- [Office 365 overschrijven Vanaf: beleid voor adreshandhaving](how-office-365-validates-the-from-address.md#Override)

- [Andere manieren om cybercriminaliteit in Office 365 te voorkomen en te beschermen](how-office-365-validates-the-from-address.md#OtherProtection)

Verzenden namens een andere gebruiker wordt niet beïnvloed door deze wijziging, voor meer details, lees Terry Zink's blog "[Wat bedoelen we als we verwijzen naar de 'afzender' van een e-mail?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".

### <a name="all-messages-must-include-a-valid-from-address"></a>Alle berichten moeten een geldig Vanaf: adres bevatten
<a name="MustIncludeFromAddress"> </a>

Sommige geautomatiseerde berichten bevatten geen Van: adres wanneer ze worden verzonden. In het verleden, toen Office 365 of Outlook.com een bericht ontvangen zonder een Van: adres, heeft de service de volgende standaard van: adres naar het bericht toegevoegd om het te laten bezorgen:

```
From: <>
```

Vanaf 9 november 2017 rolt Office 365 wijzigingen uit in zijn datacenters en e-mailservers, waardoor een nieuwe regel wordt afgedwongen waarbij berichten zonder From: adres niet langer worden geaccepteerd door Office 365 of Outlook.com. In plaats daarvan moeten alle door Office 365 ontvangen berichten al een geldig Van: adres bevatten. Anders wordt het bericht verzonden naar de map Ongewenste e-mail of Verwijderde items in Outlook.com en Office 365.

### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Syntaxisoverzicht: geldige notatie voor het adres Van voor Office 365
<a name="SyntaxOverviewFromAddress"> </a>

De indeling voor de waarde van het Adres Van: wordt in detail gedefinieerd op verschillende RFC's. Er zijn veel variaties op het aanpakken en wat kan worden beschouwd als geldig of ongeldig. Om het eenvoudig te houden, raadt Microsoft u aan de volgende indeling en definities te gebruiken:

```
From: "displayname " <emailaddress >
```

Waar:

- (Optioneel)  *displayname* is een woordgroep waarin de eigenaar van het e-mailadres wordt beschreven. Dit kan bijvoorbeeld een gebruiksvriendelijkere naam zijn om de afzender te beschrijven dan de naam van het postvak. Het gebruik van een weergavenaam is optioneel. Als u er echter voor kiest om een weergavenaam te gebruiken, raadt Microsoft u aan deze altijd in te sluiten binnen aanhalingstekens zoals afgebeeld.

- (Vereist)  *e-mailadres* bestaat uit:

  ```
  local-part @domain
  ```

    Waar:

  - (Vereist)  *lokaal deel* is een tekenreeks die het postvak identificeert dat aan het adres is gekoppeld. Dit is uniek binnen het domein. Vaak wordt de gebruikersnaam of GUID van de postvakeigenaar gebruikt als de waarde voor het lokale gedeelte.

  - (Vereist)  *domein* is de volledig gekwalificeerde domeinnaam (FQDN) van de e-mailserver die het postvak host dat is geïdentificeerd door het lokale deel van het e-mailadres.

### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Indeling van het Adres Van als u geen weergavenaam opneemt
<a name="FormatNoDisplayName"> </a>

Een goed geformatteerd Van: adres dat geen weergavenaam bevat, bevat slechts één e-mailadres met of zonder hoekhaakjes. Microsoft raadt u aan de hoekhaakjes niet te scheiden met spaties. Bovendien, niet iets opnemen na het e-mailadres.

De volgende voorbeelden zijn geldig:

```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

Het volgende voorbeeld is geldig, maar wordt niet aanbevolen omdat het spaties bevat tussen de hoekhaakjes en het e-mailadres:

```
From: < sender@contoso.com >
```

Het volgende voorbeeld is ongeldig omdat het tekst na het e-mailadres bevat:

```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Indeling van het Adres Van: als u een weergavenaam opneemt
<a name="FormatDisplayName"> </a>

Voor From: adressen die een waarde voor de weergavenaam bevatten, zijn de volgende regels van toepassing:

- Als het afzenderadres een weergavenaam bevat en de weergavenaam een komma bevat, moet de weergavenaam worden ingesloten binnen aanhalingstekens. Bijvoorbeeld:

    Het volgende voorbeeld is geldig:

  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    Het volgende voorbeeld is niet geldig:

  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    De weergavenaam niet inaanhalingstekens worden bijgesloten als die weergavenaam een komma bevat, is ongeldig volgens RFC 5322.

    Als aanbevolen praktijk plaatst u aanhalingstekens rond de weergavenaam, ongeacht of er al dan niet een komma in de weergavenaam is.

- Als het afzenderadres een weergavenaam bevat, moet het e-mailadres worden ingesloten binnen hoekhaakjes.

    Als aanbevolen praktijk raadt Microsoft u ten zeerste aan een ruimte in te voegen tussen de weergavenaam en het e-mailadres.

### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Aanvullende voorbeelden van geldig en ongeldig Vanaf: adressen
<a name="Examples"> </a>

- Geldig:

  ```
  From: "Office 365" <sender@contoso.com>
  ```

- Ongeldig. Het e-mailadres is niet bijgesloten met hoekhaakjes:

  ```
  From: Office 365 sender@contoso.com
  ```

- Geldig, maar niet aanbevolen. De weergavenaam staat niet tussen aanhalingstekens. Als beste praktijk, altijd aanhalingstekens rond de weergavenaam:

  ```
  From: Office 365 <sender@contoso.com>
  ```

- Ongeldig. Alles is ingesloten binnen aanhalingstekens, niet alleen de weergavenaam:

  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- Ongeldig. Er zijn geen hoekhaakjes rond het e-mailadres:

  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- Ongeldig. Er is geen ruimte tussen de weergavenaam en de linkerhoek:

  ```
  From: Office 365<sender@contoso.com>
  ```

- Ongeldig. Er is geen ruimte tussen het sluitende aanhalingsteken rond de weergavenaam en de linkerhoekbeugel.

  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Automatische antwoorden op uw aangepaste domein onderdrukken zonder het beleid Van:
<a name="SuppressAutoReply"> </a>

Met de nieuwe Van: beleidshandhaving kun je \< \> From: niet meer gebruiken om auto-antwoorden te onderdrukken. In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein.

De MX-record (mail exchanger) is een resourcerecord in DNS die de e-mailserver identificeert die e-mail voor uw domein ontvangt. Automatische antwoorden (en alle antwoorden) worden natuurlijk onderdrukt omdat er geen gepubliceerd adres is waarop de reagerende server berichten kan verzenden.

Wanneer u een null MX-record instelt voor uw aangepaste domein:

- Kies een domein waaruit u berichten wilt verzenden die geen e-mail accepteren (ontvangen). Als uw primaire domein bijvoorbeeld contoso.com is, u kiezen voor noreply.contoso.com.

- Stel de null MX-record voor uw domein in. Een null MX record bestaat uit een enkele stip, bijvoorbeeld:

  ```
  noreply.contoso.com IN MX .
  ```

Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.

### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Office 365 overschrijven Vanaf: beleid voor adreshandhaving
<a name="Override"> </a>

Nadat de uitrol van het nieuwe beleid is voltooid, u dit beleid alleen omzeilen voor binnenkomende e-mail die u van Office 365 ontvangt met behulp van een van de volgende methoden:

- IP-lijstmet toestaan

- Regels voor de stroomstroom van Exchange Online

Microsoft raadt ten zeerste aan om de handhaving van het From:-beleid te overschrijven. Als u dit beleid overschrijft, kan het risico van blootstelling van uw organisatie aan spam, phishing en andere cybercriminaliteit toenemen.

U dit beleid niet overschrijven voor uitgaande e-mail die u in Office 365 verzendt. Bovendien staat Outlook.com geen overschrijvingen van welke aard dan ook toe, zelfs niet via ondersteuning.

### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Andere manieren om cybercriminaliteit in Office 365 te voorkomen en te beschermen
<a name="OtherProtection"> </a>

Zie [Aanbevolen procedures voor beveiliging voor Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)voor meer informatie over hoe u uw organisatie versterken tegen cybercriminaliteit zoals phishing, spam, datalekken en andere bedreigingen.

## <a name="related-topics"></a>Gerelateerde onderwerpen

[Backscatter messages and EOP](backscatter-messages-and-eop.md)(Backscatter-berichten en EOP)
