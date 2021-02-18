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
description: Beheerders kunnen informatie krijgen over de typen e-mailadressen die worden geaccepteerd of geweigerd door Exchange Online Protection (EOP) en Outlook.com om phishing te voorkomen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ced200c2e521533c1dec8a9d0917add7ca058f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287817"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Hoe EOP het Van-adres valideert om phishing te voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Phishing-aanvallen vormen een constante bedreiging voor elke e-mailorganisatie. Naast het gebruik van e-mailadressen met vervalste [(vervalste) afzenders](anti-spoofing-protection.md)gebruiken aanvallers vaak waarden in het Van-adres die in strijd zijn met internetstandaarden. Om dit type phishing te voorkomen, vereisen Exchange Online Protection (EOP) en Outlook.com nu inkomende berichten met een RFC-compatibel Van-adres, zoals beschreven in dit artikel. Dit afdwingen is ingeschakeld in november 2017.

**Opmerkingen**:

- Als u regelmatig e-mail ontvangt van organisaties die een verkeerd geadresseerde Van-adres hebben, zoals beschreven in dit artikel, moedigt u deze organisaties aan om hun e-mailservers bij te werken zodat ze voldoen aan moderne beveiligingsstandaarden.

- Deze vereisten gelden niet voor het veld gerelateerde afzender (dat wordt gebruikt door Verzenden namens en adressenlijsten). Zie het volgende blogbericht voor meer informatie: Wat betekenen we als we naar de ['afzender'](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)van een e-mailbericht verwijzen?

## <a name="an-overview-of-email-message-standards"></a>Een overzicht van standaarden voor e-mailberichten

Een standaard SMTP-e-mailbericht bestaat uit een *envelop met berichten* en berichtinhoud. De envelop met berichten bevat informatie die is vereist voor het verzenden en bezorgen van het bericht tussen SMTP-servers. De inhoud van het bericht bevat berichtkopvelden (gezamenlijk de berichtkop *genoemd)* en de berichttekst. De berichtvelop wordt beschreven in [RFC 5321](https://tools.ietf.org/html/rfc5321)en de berichtkop wordt beschreven in [RFC 5322.](https://tools.ietf.org/html/rfc5322) Geadresseerden zien de feitelijke berichtvelopop niet, omdat deze wordt gegenereerd door het verzendingsproces voor berichten en niet daadwerkelijk deel uitmaakt van het bericht.

- Het adres (ook wel bekend als het `5321.MailFrom` MAIL **FROM-adres,** de afzender van P1 of de afzender van de envelop) is het e-mailadres dat wordt gebruikt in de SMTP-verzending van het bericht. Dit e-mailadres wordt  meestal opgenomen in het koptekstveld Retourpad in de berichtkoptekst (hoewel de afzender een ander **e-mailadres** voor het retourpad kan aanwijzen).

- De afzender (ook wel het Van-adres of P2 genoemd) is het e-mailadres in het veld Van en is het e-mailadres van de afzender dat wordt weergegeven `5322.From` in e-mail clients.  Het van-adres heeft de focus op de vereisten in dit artikel.

Het van-adres wordt in detail gedefinieerd voor verschillende RFCs (bijvoorbeeld RFC 5322 secties 3.2.3, 3.4 en 3.4.1 en [RFC 3696).](https://tools.ietf.org/html/rfc3696) Er zijn veel variaties op adressering en wat wordt beschouwd als geldig of ongeldig. Om het eenvoudig te houden, raden we de volgende opmaak en definities aan:

`From: "Display Name" <EmailAddress>`

- **Weergavenaam:** een optioneel zinsdeel waarin de eigenaar van het e-mailadres wordt beschreven.

  - Het is raadzaam de weergavenaam altijd tussen dubbele aanhalingstekens (") te plaatsen, zoals hier wordt weergegeven. Als de weergavenaam een komma bevat, moet u de tekenreeks tussen dubbele aanhalingstekens plaatsen per RFC 5322. 
  - Als het Van-adres een weergavenaam bevat, moet de waarde EmailAddress tussen hoekhaken (< >) staan, zoals weergegeven.
  - Microsoft raadt u ten zeerste aan om een spatie in te voegen tussen de weergavenaam en het e-mailadres.

- **EmailAddress:** voor een e-mailadres wordt de notatie `local-part@domain` gebruikt:

  - **lokaal-onderdeel:** een tekenreeks die het postvak aangeeft dat aan het adres is gekoppeld. Deze waarde is uniek binnen het domein. Vaak wordt de gebruikersnaam of GUID van de eigenaar van het postvak gebruikt.
  - **domein:** de FQDN(Fully Qualified Domain Name) van de e-mailserver die het postvak host dat wordt geïdentificeerd door het lokale gedeelte van het e-mailadres.

  Dit zijn enkele aanvullende overwegingen voor de waarde van EmailAddress:

  - Slechts één e-mailadres.
  - Het is raadzaam de haakjes tussen de hoeken niet te scheiden met spaties.
  - Voeg geen extra tekst na het e-mailadres toe.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Voorbeelden van geldige en ongeldige Van-adressen

De volgende Van-e-mailadressen zijn geldig:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Niet aanbevolen omdat er spaties zijn tussen de haakjes en het e-mailadres.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Dit wordt niet aanbevolen omdat de weergavenaam niet tussen dubbele aanhalingstekens wordt weergegeven.)

De volgende Van-e-mailadressen zijn ongeldig:

- **Nee van-adres:** sommige geautomatiseerde berichten bevatten geen Van-adres. In het verleden, toen Microsoft 365 of Outlook.com een bericht zonder een Van-adres ontving, heeft de service het volgende standaard Van:-adres toegevoegd om het bericht te leveren:

  `From: <>`

  Berichten met een leeg Van-adres worden nu niet meer geaccepteerd.

- `From: Microsoft 365 sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres wordt niet tussen haakjes geplaatst.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Tekst na het e-mailadres.)

- `From: Sender, Example <sender.example@contoso.com>` (De weergavenaam bevat een komma, maar staat niet tussen dubbele aanhalingstekens.)

- `From: "Microsoft 365 <sender@contoso.com>"` (De hele waarde wordt onjuist tussen dubbele aanhalingstekens geplaatst.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (De weergavenaam is aanwezig, maar het e-mailadres wordt niet tussen haakjes geplaatst.)

- `From: Microsoft 365<sender@contoso.com>` (Geen spatie tussen de weergavenaam en de linkerhoek.)

- `From: "Microsoft 365"<sender@contoso.com>` (Geen spatie tussen de dubbele aanhalingstekens sluiten en de haak links.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Automatische antwoorden op uw aangepaste domein onderdrukken

U kunt de waarde niet gebruiken om `From: <>` automatische antwoorden te onderdrukken. In plaats daarvan moet u een null MX-record instellen voor uw aangepaste domein. Automatische antwoorden (en alle antwoorden) worden op natuurlijke wijze onderdrukken omdat er geen gepubliceerd adres is waar de server berichten naar kan verzenden.

- Kies een e-maildomein dat geen e-mail kan ontvangen. Als uw primaire domein bijvoorbeeld contoso.com is, kunt u noreply.contoso.com.

- De Null MX-record voor dit domein bestaat uit één punt.

Bijvoorbeeld:

```text
noreply.contoso.com IN MX .
```

Zie DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het instellen van MX-records.

Zie [RFC 7505](https://tools.ietf.org/html/rfc7505)voor meer informatie over het publiceren van een null MX.

## <a name="override-from-address-enforcement"></a>Overschrijven van adres afdwingen

Als u de Van-adresvereisten voor inkomende e-mail wilt omzeilen, kunt u de regels voor de toegestane lijst met IP-adressen (verbindingsfilters) of regels voor de e-mailstroom (ook wel transportregels genoemd) gebruiken, zoals wordt beschreven in Lijsten met veilige afzenders maken [in Microsoft 365.](create-safe-sender-lists-in-office-365.md)

U kunt de van-adresvereisten niet overschrijven voor uitgaande e-mail die u verzendt vanuit Microsoft 365. Daarnaast kan Outlook.com geen enkele vorm van overschrijven toestaan, zelfs niet via ondersteuning.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andere manieren om cybercriminaliteit te voorkomen en te beschermen in Microsoft 365

Zie de tien belangrijkste manieren om microsoft [365](../../admin/security-and-compliance/secure-your-business-data.md)voor bedrijven te beveiligen voor meer informatie over hoe u uw organisatie kunt versterken tegen phishing, spam, gegevensinbreuken en andere bedreigingen.
