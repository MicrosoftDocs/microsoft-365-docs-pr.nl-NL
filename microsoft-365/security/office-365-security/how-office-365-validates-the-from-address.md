---
title: Hoe EOP het Van-adres valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de typen e-mailadressen die worden geaccepteerd of geweigerd door Exchange Online Protection (EOP) en Outlook.com om phishing te voorkomen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204183"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Hoe EOP het Van-adres valideert om phishing te voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Phishingaanvallen vormen een constante bedreiging voor elke e-mailorganisatie. Naast het gebruik van [vervalste e-mailadressen van (vervalste) afzenders](anti-spoofing-protection.md)gebruiken aanvallers vaak waarden in het Van-adres die in strijd zijn met internetstandaarden. Om dit type phishing te voorkomen, hebben Exchange Online Protection (EOP) en Outlook.com nu inkomende berichten nodig om een RFC-compatibel Van-adres op te nemen, zoals beschreven in dit artikel. Deze handhaving is ingeschakeld in november 2017.

**Opmerkingen**:

- Als u regelmatig e-mail ontvangt van organisaties die Van-adressen hebben misvormd, zoals beschreven in dit artikel, moedigt u deze organisaties aan hun e-mailservers bij te werken om te voldoen aan moderne beveiligingsstandaarden.

- Het gerelateerde veld Afzender (gebruikt door Verzenden namens en adressenlijsten) wordt niet beïnvloed door deze vereisten. Zie het volgende blogbericht voor meer informatie: Wat betekenen we als we verwijzen naar de ['afzender' van een e-mailbericht?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).

## <a name="an-overview-of-email-message-standards"></a>Een overzicht van de standaarden voor e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud. De envelop met berichten bevat informatie die nodig is voor het verzenden en verzenden van het bericht tussen SMTP-servers. De berichtinhoud bevat berichtkopvelden (gezamenlijk de *berichtkop* genoemd) en de hoofdtekst van het bericht. De bericht envelop wordt beschreven in [RFC 5321](https://tools.ietf.org/html/rfc5321)en de berichtkop wordt beschreven in [RFC 5322](https://tools.ietf.org/html/rfc5322). Geadresseerden zien nooit de werkelijke bericht envelop omdat deze wordt gegenereerd door het berichttransmissieproces en het bericht niet deel uitmaakt van het bericht.

- Het `5321.MailFrom` adres (ook wel mail **from-adres,** P1-afzender of afzender van de envelop genoemd) is het e-mailadres dat wordt gebruikt bij de SMTP-verzending van het bericht. Dit **e-mailadres** wordt meestal opgenomen in het veld Koptekst van het retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor retourpaden kan aanwijzen).

- De afzender (ook wel het Van-adres of de afzender van P2 genoemd) is het e-mailadres in het veld Koptekst van Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail  clients. Het Van-adres is de focus van de vereisten in dit artikel.

Het Van-adres wordt in detail gedefinieerd in verschillende RFC's (bijvoorbeeld RFC 5322 secties 3.2.3, 3.4 en 3.4.1 en [RFC 3696).](https://tools.ietf.org/html/rfc3696) Er zijn veel variaties op adressering en wat als geldig of ongeldig wordt beschouwd. Om het eenvoudig te houden, raden we de volgende opmaak en definities aan:

`From: "Display Name" <EmailAddress>`

- **Weergavenaam:** een optionele woordgroep waarin de eigenaar van het e-mailadres wordt beschreven.

  - U wordt aangeraden de weergavenaam altijd tussen dubbele aanhalingstekens (") te plaatsen, zoals wordt weergegeven. Als de weergavenaam een komma bevat, moet u de tekenreeks tussen dubbele aanhalingstekens per RFC 5322 plaatsen. 
  - Als het Van-adres een weergavenaam bevat, moet de e-mailadreswaarde tussen haakjes (< >) staan, zoals wordt weergegeven.
  - Microsoft raadt ten zeerste aan om een spatie in te voegen tussen de weergavenaam en het e-mailadres.

- **EmailAddress:** Een e-mailadres gebruikt de notatie `local-part@domain` :

  - **lokaal deel:** een tekenreeks die het postvak identificeert dat aan het adres is gekoppeld. Deze waarde is uniek binnen het domein. Vaak wordt de gebruikersnaam of GUID van de eigenaar van het postvak gebruikt.
  - **domein:** De volledig gekwalificeerde domeinnaam (FQDN) van de e-mailserver die het postvak host dat is geïdentificeerd door het lokale gedeelte van het e-mailadres.

  Dit zijn enkele extra aandachtspunten voor de waarde EmailAddress:

  - Slechts één e-mailadres.
  - U wordt aangeraden de hoekhaken niet te scheiden van spaties.
  - Voeg geen extra tekst toe na het e-mailadres.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Voorbeelden van geldige en ongeldige Van-adressen

De volgende Van e-mailadressen zijn geldig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Niet aanbevolen omdat er spaties zijn tussen de haakjes en het e-mailadres.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Niet aanbevolen omdat de weergavenaam niet tussen dubbele aanhalingstekens staat.)

De volgende Van e-mailadressen zijn ongeldig:

- **Nee van-adres:** Sommige geautomatiseerde berichten bevatten geen Van-adres. In het verleden, wanneer Microsoft 365 of Outlook.com een bericht zonder een Van-adres heeft ontvangen, heeft de service de volgende standaard van: adres toegevoegd om het bericht te leveren:

  `From: <>`

  Berichten met een leeg Van-adres worden nu niet meer geaccepteerd.

- `From: Microsoft 365 sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres is niet tussen haakjes geplaatst.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Tekst na het e-mailadres.)

- `From: Sender, Example <sender.example@contoso.com>` (De weergavenaam bevat een komma, maar staat niet tussen dubbele aanhalingstekens.)

- `From: "Microsoft 365 <sender@contoso.com>"` (De hele waarde is onjuist tussen dubbele aanhalingstekens geplaatst.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres is niet tussen haakjes geplaatst.)

- `From: Microsoft 365<sender@contoso.com>` (Geen spatie tussen de weergavenaam en de haak met de linkerhoek.)

- `From: "Microsoft 365"<sender@contoso.com>` (Geen spatie tussen het dubbele aanhalingsteken sluiten en de haak met de linkerhoek.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatische antwoorden op uw aangepaste domein onderdrukken

U kunt de waarde niet gebruiken om automatische antwoorden `From: <>` te onderdrukken. In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein. Automatische antwoorden (en alle antwoorden) worden op natuurlijke wijze onderdrukt omdat er geen gepubliceerd adres is waar de server die op reageert berichten naar kan verzenden.

- Kies een e-maildomein dat geen e-mail kan ontvangen. Als uw primaire domein bijvoorbeeld contoso.com is, kunt u een noreply.contoso.com.

- De null MX-record voor dit domein bestaat uit één punt.

Bijvoorbeeld:

```text
noreply.contoso.com IN MX .
```

Zie DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het instellen van MX-records.

Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.

## <a name="override-from-address-enforcement"></a>Van adres afdwingen overschrijven

Als u de van-adresvereisten voor binnenkomende e-mail wilt omzeilen, kunt u de regels ip-toestaan (verbindingsfilters) of e-mailstroomregels (ook wel transportregels genoemd) gebruiken, zoals beschreven in Lijsten met veilige afzenders maken [in Microsoft 365.](create-safe-sender-lists-in-office-365.md)

U kunt de Vereisten voor Van-adres niet overschrijven voor uitgaande e-mail die u verzendt vanuit Microsoft 365. Bovendien worden Outlook.com geen overschrijvingen van welke aard dan ook toegestaan, zelfs niet via ondersteuning.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andere manieren om cybercriminaliteit te voorkomen en te beschermen in Microsoft 365

Zie Top 10 manieren om [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)voor Bedrijven-abonnementen te beveiligen voor meer informatie over hoe u uw organisatie kunt versterken tegen phishing, spam, datalekken en andere bedreigingen.