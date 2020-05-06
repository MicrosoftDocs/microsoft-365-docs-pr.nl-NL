---
title: Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen
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
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 'Om phishing te voorkomen, vereisen Microsoft 365 en Outlook.com nu RFC-naleving voor From: addresses.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef361c7009cc8903ab2721d299412b7d44a4f87c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034080"
---
# <a name="how-microsoft-365-validates-the-from-address-to-prevent-phishing"></a>Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen

Microsoft 365 e-mailaccounts ontvangen een steeds groter aantal phishing-aanvallen. Naast het gebruik van [vervalste (vervalste) afzender e-mailadressen](anti-spoofing-protection.md), aanvallers gebruiken vaak waarden in de Van adres die internet normen schenden. Om dit soort phishing te voorkomen, vereisen Microsoft 365 en Outlook.com nu binnenkomende berichten om een RFC-compatibel Adres op te nemen zoals beschreven in dit onderwerp. Deze handhaving werd in november 2017 mogelijk gemaakt.

**Opmerkingen**:

- Als u regelmatig e-mail ontvangt van organisaties die verkeerd zijn vervormd van adressen zoals beschreven in dit onderwerp, moedigt u deze organisaties aan om hun e-mailservers bij te werken om te voldoen aan moderne beveiligingsstandaarden.

- Het veld gerelateerde afzender (gebruikt door Verzenden namens en mailinglijsten) wordt niet beïnvloed door deze vereisten. Zie voor meer informatie de volgende blogpost: [Wat bedoelen we als we verwijzen naar de 'afzender' van een e-mail?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Een overzicht van de normen voor e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *berichtenvelop* en berichtinhoud. De berichtenvelop bevat informatie die nodig is voor het verzenden en leveren van het bericht tussen SMTP-servers. De inhoud van het bericht bevat teksttekstvelden (gezamenlijk de *berichtkop genoemd)* en de berichttekst. De berichtenvelop wordt beschreven in [RFC 5321](https://tools.ietf.org/html/rfc5321)en de berichtkop wordt beschreven in [RFC 5322](https://tools.ietf.org/html/rfc5322). Ontvangers zien nooit de werkelijke berichtenvelop omdat deze wordt gegenereerd door het berichtoverdrachtsproces en het is eigenlijk geen onderdeel van het bericht.

- Het `5321.MailFrom` adres (ook bekend als het **e-mailadres van** het adres, de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-transmissie van het bericht. Dit e-mailadres wordt meestal opgenomen in het koptekstveld **Return-Path** in de berichtkop (hoewel het mogelijk is dat de afzender een ander **e-mailadres van het retourpad** aanwijst).

- Het `5322.From` (ook wel bekend als de Afzender Van of P2) is het e-mailadres in het veld **Van** koptekst en is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients. Het Adres van Het is de nadruk van de vereisten in dit onderwerp.

Het Adres Van wordt in detail gedefinieerd over verschillende RFC's (bijvoorbeeld RFC 5322-secties 3.2.3, 3.4 en 3.4.1 en [RFC 3696](https://tools.ietf.org/html/rfc3696)). Er zijn veel variaties op het adresseren en wat wordt beschouwd als geldig of ongeldig. Om het simpel te houden, raden we de volgende indeling en definities aan:

`From: "Display Name" <EmailAddress>`

- **Weergavenaam:** een optionele woordgroep die de eigenaar van het e-mailadres beschrijft.

  - We raden u aan de weergavenaam altijd in dubbele aanhalingstekens (") zoals weergegeven, in te sluiten. Als de weergavenaam een komma bevat, _moet_ u de tekenreeks in dubbele aanhalingstekens per RFC 5322 bijsluiten.
  - Als het Van-adres een weergavenaam bevat, moet de waarde Van Mailadres worden ingesloten in hoekhaakjes (< >) zoals weergegeven.
  - Microsoft raadt u ten zeerste aan een spatie in te voegen tussen de weergavenaam en het e-mailadres.

- **E-mailadres:** Een e-mailadres maakt gebruik van de indeling: `local-part@domain`

  - **lokaal deel**: een tekenreeks die het postvak identificeert dat aan het adres is gekoppeld. Deze waarde is uniek binnen het domein. Vaak wordt de gebruikersnaam of GUID van de eigenaar van het postvak gebruikt.
  - **domein:** de volledig gekwalificeerde domeinnaam (FQDN) van de e-mailserver die het postvak host dat is geïdentificeerd door het lokale deel van het e-mailadres.

  Dit zijn enkele aanvullende overwegingen voor de waarde Van E-mailadres:

  - Slechts één e-mailadres.
  - Wij raden u aan de hoekbeugels niet te scheiden van spaties.
  - Voeg geen extra tekst toe na het e-mailadres.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Voorbeelden van geldig en ongeldig van adressen

Het volgende Van e-mailadressen zijn geldig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >`(Niet aanbevolen omdat er spaties zijn tussen de hoekhaakjes en het e-mailadres.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>`(Niet aanbevolen omdat de weergavenaam niet is ingesloten met dubbele aanhalingstekens.)

Het volgende Van e-mailadressen zijn ongeldig:

- **Geen adres:** Sommige geautomatiseerde berichten bevatten geen Van-adres. In het verleden, toen Microsoft 365 of Outlook.com een bericht zonder adres van Het Adres ontving, voegde de service de volgende standaardvan: adres toe om het bericht deliverable te maken:

  `From: <>`

  Nu worden berichten met een leeg Van-adres niet meer geaccepteerd.

- `From: Microsoft 365 sender@contoso.com`(De weergavenaam is aanwezig, maar het e-mailadres is niet in gesloten in hoekhaakjes.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Tekst na het e-mailadres.)

- `From: Sender, Example <sender.example@contoso.com>`(De weergavenaam bevat een komma, maar is niet ingesloten met dubbele aanhalingstekens.)

- `From: "Microsoft 365 <sender@contoso.com>"`(De hele waarde is onjuist ingesloten in dubbele aanhalingstekens.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(De weergavenaam is aanwezig, maar het e-mailadres is niet in gesloten in hoekhaakjes.)

- `From: Microsoft 365<sender@contoso.com>`(Geen ruimte tussen de weergavenaam en de linkerhoekbeugel.)

- `From: "Microsoft 365"<sender@contoso.com>`(Geen ruimte tussen het afsluitende dubbele aanhalingsteken en de linkerhoekhaak.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatische antwoorden op uw aangepaste domein onderdrukken

U de waarde `From: <>` niet gebruiken om automatische antwoorden te onderdrukken. In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein. Automatische antwoorden (en alle antwoorden) worden natuurlijk onderdrukt omdat er geen gepubliceerd adres is waar naar de reagerende server berichten kan worden verzonden.

- Kies een e-maildomein dat geen e-mail kan ontvangen. Als uw primaire domein bijvoorbeeld contoso.com is, u noreply.contoso.com kiezen.

- De null MX-record voor dit domein bestaat uit één periode.

Bijvoorbeeld:

```text
noreply.contoso.com IN MX .
```

Zie [DNS-records maken bij elke DNS-hostingprovider voor Microsoft 365 voor](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)meer informatie over het instellen van MX-records.

Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.

## <a name="override-from-address-enforcement"></a>Overschrijven van adreshandhaving

Als u de vereisten voor binnenkomende e-mail wilt omzeilen, u de IP-lijst met toegestane verbindingen (verbindingsfilter) of e-mailstroomregels (ook wel transportregels genoemd) gebruiken, zoals beschreven in [Lijsten met veilige afzendermaken in Microsoft 365.](create-safe-sender-lists-in-office-365.md)

U de vereisten voor het adres van De u niet overschrijven voor uitgaande e-mail die u vanuit Microsoft 365 verzendt. Bovendien zal Outlook.com geen overschrijvingen van welke aard dan ook toestaan, zelfs niet via ondersteuning.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andere manieren om cybercriminaliteit te voorkomen en te beschermen in Microsoft 365

Zie [Top 10 manieren om Microsoft 365 voor bedrijfsabonnementen te beveiligen](../../admin/security-and-compliance/secure-your-business-data.md)voor meer informatie over hoe u uw organisatie versterken tegen phishing, spam, datalekken en andere bedreigingen.