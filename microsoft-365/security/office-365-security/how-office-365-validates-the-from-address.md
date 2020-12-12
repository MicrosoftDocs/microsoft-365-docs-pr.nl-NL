---
title: Hoe EOP het van-adres valideert om phishing te voorkomen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie vinden over de typen e-mailadressen die worden geaccepteerd of geweigerd door Exchange Online Protection (EOP) en Outlook.com om phishing te voorkomen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25fbca8fa5d264a212ac25e2035bffde0819383d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659652"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Hoe EOP het van-adres valideert om phishing te voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Phishing-aanvallen vormen een constante bedreiging voor elke e-mail organisatie. Naast het gebruik van [valse vervalste e-mailadressen van e-mailadressen](anti-spoofing-protection.md), kunnen aanvallers ook waarden gebruiken in het van-adres dat schendt voor internetstandaarden. Om dit type phishing te helpen voorkomen, hebben inkomende berichten via Exchange Online Protection (EOP) en Outlook.com voortaan inkomende berichten opgenomen, zodat een RFC-compatibel adres wordt opgenomen in dit artikel. Dit executie is ingeschakeld in november 2017.

**Opmerkingen**:

- Als u regelmatig e-mailberichten ontvangt van organisaties die een verkeerd gespelde fout hebben op basis van adressen zoals in dit artikel wordt beschreven, raden we u aan deze organisaties te laten bijwerken dat hun e-mailservers voldoen aan de moderne beveiligings normen

- Het veld voor de bijbehorende afzender (voor verzenden namens en adressenlijsten) wordt niet beïnvloed door deze vereisten. Voor meer informatie raadpleegt u het volgende blogbericht: [Wat betekenen we wanneer we naar de afzender van een e-mailbericht verwijzen?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Een overzicht van de standaarden voor e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en de inhoud van het bericht. De envelop bericht bevat informatie die nodig is voor het verzenden en het verzenden van het bericht tussen SMTP-servers. De inhoud van het bericht bevat berichtkop velden (gezamenlijk de kop van het *e-mailbericht* genoemd) en de berichttekst. De envelop van het bericht wordt beschreven in [rfc 5321](https://tools.ietf.org/html/rfc5321)en de kop van het e-mailbericht wordt beschreven in [RFC 5322](https://tools.ietf.org/html/rfc5322). Geadresseerden zien de envelop met het werkelijke bericht niet omdat deze wordt gegenereerd door het proces voor het verzenden van berichten en het maakt niet uit van het bericht.

- Het `5321.MailFrom` adres (ook wel **e-mail adres van** de afzender, de afzender van P1 of de afzender) is het e-mailadres dat wordt gebruikt in de SMTP-overdracht van het bericht. Dit e-mailadres wordt meestal opgenomen in het veld voor **de veldnamenrij in de kop van** het bericht (hoewel het mogelijk is dat de afzender een ander e-mailadres voor het **retour traject** aanwijst).

- De `5322.From` (ook bekend als de afzender van address of P2) is het e-mailadres in het veld **van** koptekst en het e-mailadres van de afzender dat wordt weergegeven in e-mailclients. Het van-adres is de focus van de vereisten in dit artikel.

Het van-adres wordt uitvoerig beschreven in diverse Rfc's (bijvoorbeeld RFC 5322, punt 3.2.3, 3,4 en 3.4.1, en [RFC 3696](https://tools.ietf.org/html/rfc3696)). Er zijn veel variaties op de adressering en wat wordt als geldig of ongeldig beschouwd. Om de sjabloon eenvoudig te houden, raden we de volgende opmaak en definities aan:

`From: "Display Name" <EmailAddress>`

- **Weergavenaam**: een optionele woordgroep waarmee de eigenaar van het e-mailadres wordt beschreven.

  - U wordt aangeraden de weergavenaam altijd tussen dubbele aanhalingstekens (") te plaatsen, zoals getoond. Als de weergavenaam een komma bevat, _moet_ u de tekenreeks tussen dubbele aanhalingstekens plaatsen per RFC 5322.
  - Als het van-adres een weergavenaam bevat, moet de waarde van EmailAddress tussen punthaken (< >) worden weergegeven.
  - U wordt ten zeerste aangeraden een spatie in te voegen tussen de weergavenaam en het e-mailadres.

- **EmailAddress**: voor een e-mailadres wordt de volgende indeling gebruikt `local-part@domain` :

  - **local-part**: een tekenreeks die het postvak identificeert dat is gekoppeld aan het adres. Deze waarde is uniek binnen het domein. Vaak wordt de gebruikersnaam of GUID van het postvak van de eigenaar gebruikt.
  - **Domain**: de FQDN-naam (Fully Qualified Domain Name) van de e-mailserver waarop het postvak wordt gehost dat wordt aangeduid door het lokale deel van het e-mailadres.

  Hier volgen enkele aanvullende aandachtspunten voor de waarde van EmailAddress:

  - Slechts één e-mailadres.
  - We raden u aan dat u de haken met spaties niet scheidt.
  - Neem geen aanvullende tekst onder het e-mailadres.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Voorbeelden van geldige en ongeldige adressen van adressen

De volgende e-mailadressen zijn geldig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Niet aanbevolen omdat er spaties tussen de punthaken en het e-mailadres staan.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Wordt niet aanbevolen, omdat de weergavenaam niet tussen dubbele aanhalingstekens is geplaatst.)

De volgende e-mailadressen zijn ongeldig:

- **Nee van-adres**: sommige geautomatiseerde berichten bevatten geen van-adres. Wanneer Microsoft 365 of Outlook.com in het verleden een bericht heeft ontvangen zonder een van-adres, heeft de service het volgende standaard van-adres toegevoegd aan het bericht product:

  `From: <>`

  Berichten met een leeg van-adres worden nu niet meer geaccepteerd.

- `From: Microsoft 365 sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres staat niet tussen punthaken.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Tekst na het e-mailadres)

- `From: Sender, Example <sender.example@contoso.com>` (De weergavenaam bevat een komma, maar staat niet tussen dubbele aanhalingstekens).

- `From: "Microsoft 365 <sender@contoso.com>"` (De volledige waarde is een onjuiste waarde tussen dubbele aanhalingstekens.

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres staat niet tussen punthaken.)

- `From: Microsoft 365<sender@contoso.com>` (Geen spatie tussen de naam van de weergave en de punthaak links.)

- `From: "Microsoft 365"<sender@contoso.com>` (Geen spatie tussen de dubbele aanhalingstekens en de punthaak links

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatisch beantwoorden met uw aangepaste domein onderdrukken

U kunt de waarde niet gebruiken `From: <>` om automatisch antwoord te onderdrukken. In plaats daarvan moet u een lege MX-record voor uw aangepaste domein instellen. Automatisch beantwoorden (en alle antwoorden) worden natuurlijk niet doorgeslagen omdat er geen gepubliceerd adres is waarop de antwoord server berichten kan verzenden.

- Kies een e-mail domein dat geen e-mail kan ontvangen. Als uw primaire domein bijvoorbeeld contoso.com is, kunt u noreply.contoso.com kiezen.

- De lege MX-record voor dit domein bevat één periode.

Bijvoorbeeld:

```text
noreply.contoso.com IN MX .
```

Zie [DNS-records maken bij een DNS-hosting provider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het instellen van MX-records.

Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null-waarde (null).

## <a name="override-from-address-enforcement"></a>Opheffen van adres afdwingen

Als u niet wilt dat de van toepassing zijnde adressen voor inkomende e-mail wordt gebruikt, kunt u in de lijst met veilige afzenders (ook wel een verbinding maken met behulp van de lijst met [veilige afzenders](create-safe-sender-lists-in-office-365.md)) of e-mail stroom regels (ook wel de gebruikte transportregels) in microsoft 365

U kunt de van-adres vereisten voor uitgaande e-mail die u vanuit Microsoft 365 verzendt niet overschrijven. Daarnaast mag Outlook.com geen overschrijvingen van welke aard dan ook ondersteunen.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andere manieren om te voorkomen dat u cybercrimes in Microsoft 365

Zie de [tien beste manieren om uw abonnement op Microsoft 365 voor bedrijven te beveiligen](../../admin/security-and-compliance/secure-your-business-data.md)voor meer informatie over hoe u uw organisatie kunt versterken tegen phishing en spam, de schending van gegevens en andere bedreigingen.
