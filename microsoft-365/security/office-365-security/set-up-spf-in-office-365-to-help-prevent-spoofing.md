---
title: SPF instellen om adresvervalsing te helpen voorkomen
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u een DNS-record (Domain Name Service) bijwerkt, zodat u SPF (Sender Policy Framework) kunt gebruiken met uw aangepaste domein in Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 828d76b95a1e3f8d1a1851121d28603a1922f486
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538985"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>SPF instellen om adresvervalsing te helpen voorkomen

- [Vereisten](#prerequisites)
- [Uw SPF TXT-record maken of bijwerken](#create-or-update-your-spf-txt-record)
- [Subdomeinen verwerken](#how-to-handle-subdomains)
- [Problemen met SPF oplossen](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

In dit artikel wordt beschreven hoe u een DNS-record (Domain Name Service) bijwerkt, zodat u SPF-e-mailverificatie (Sender Policy Framework) kunt gebruiken met uw aangepaste domein in Office 365.

Met SPF kunt u uitgaande e-mail *valideren* die wordt verzonden vanaf uw aangepaste domein (daadwerkelijk afkomstig van de persoon die deze zegt te zijn). Het is een eerste stap bij het instellen van de volledige aanbevolen methoden voor e-mailverificatie van SPF, [DKIM](use-dkim-to-validate-outbound-email.md) en [DMARC](use-dmarc-to-validate-email.md).

- [Vereisten](#prerequisites)
- [Uw SPF TXT-record maken of bijwerken](#create-or-update-your-spf-txt-record)
  - [Subdomeinen verwerken](#how-to-handle-subdomains)
- [Wat doet SPF-e-mailverificatie eigenlijk?](#what-does-spf-email-authentication-actually-do)
  - [Problemen met SPF oplossen](#troubleshooting-spf)
- [Meer informatie over SPF](#more-information-about-spf)

## <a name="prerequisites"></a>Vereisten

> [!IMPORTANT]
> Als u een **klein bedrijf** hebt of niet bekend bent met IP-adressen of DNS-configuratie, belt u uw internetdomeinregistrar (bijvoorbeeld GoDaddy, Bluehost, web.com) om hulp te vragen bij de *DNS-configuratie van SPF* (en andere methoden voor e-mailverificatie). <p> **Als u geen aangepaste URL gebruikt** (en de URL die wordt gebruikt voor Office 365 eindigt op **onmicrosoft.com**), is SPF al voor u ingesteld in de Office 365-service.

We gaan aan de slag.

De SPF TXT-record voor Office 365 wordt gemaakt in externe DNS voor aangepaste domeinen of subdomeinen. U hebt informatie nodig om de record te maken. Verzamel de volgende informatie:

- Het SPF TXT-record voor uw aangepaste domein, indien aanwezig. Zie [De informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken](../../admin/get-help-with-domains/information-for-dns-records.md)voor instructies.

- Ga naar de berichtenserver(s) en zoek de externe IP-adressen (nodig van alle on-premises berichtenservers). Bijvoorbeeld: **131.107.2.200**.

- Domeinnamen die moeten worden gebruikt voor alle domeinen van derden die u wilt opnemen in het SPF TXT-record. Sommige aanbieders van bulkmail hebben subdomeinen ingesteld voor gebruik door hun klanten. Het bedrijf MailChimp heeft bijvoorbeeld **servers.mcsv.net** opgezet.

- Zoek uit welke handhavingsregel u wilt gebruiken voor uw SPF TXT-record. De regel **-all** wordt aanbevolen. Zie voor meer informatie over andere syntaxisopties [SPF TXT-record syntaxis voor Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> Om een aangepast domein te gebruiken, vereist Office 365 dat u een Sender Policy Framework (SPF) TXT-record toevoegt aan uw DNS-record om spoofing te helpen voorkomen.

## <a name="create-or-update-your-spf-txt-record"></a>De SPF TXT-record maken of bijwerken

1. Ga na of u bekend bent met de SPF-syntaxis in de volgende tabel.

   ****

   |Element|Als u werkt met...|Gangbaar bij klanten?|Voegt u deze toe...|
   |---|---|---|---|
   |1|Elk e-mailsysteem (vereist)|Gangbaar. Alle SPF-records beginnen met deze waarde|`v=spf1`|
   |2|Exchange Online|Gangbaar|`include:spf.protection.outlook.com`|
   |3|Alleen Exchange Online|Niet gangbaar|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|Office 365 Duitsland, alleen Microsoft Cloud Duitsland|Niet gangbaar|`include:spf.protection.outlook.de`|
   |5|E-mailsysteem van derden|Niet gangbaar|`include:<domain_name>` <p> \<domain_name\> is het domein van het e-mailsysteem van derden.|
   |6|On-premises-e-mailsysteem. Bijvoorbeeld Exchange Online Protection plus een ander e-mailsysteem|Niet gangbaar|Gebruik een van deze voor elk extra e-mailsysteem: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> en \<domain_name\> zijn het IP-adres en domein van het andere e-mailsysteem waarmee e-mail namens je domein wordt verzonden.|
   |7|Elk e-mailsysteem (vereist)|Gangbaar. Alle SPF-records eindigen met deze waarde|`<enforcement rule>` <p> Dit kan een van meerdere waarden zijn. We adviseren de waarde `-all`.|
   |

2. Als u dit nog niet hebt gedaan, kunt u het SPF TXT-record maken met behulp van de syntaxis uit de tabel.

   Als u bijvoorbeeld volledig gehost bent in Office 365 (dat wil zeggen dat u geen on-premises-e-mailservers heeft) bevat uw SPF TXT-record rijen 1, 2 en 7 en ziet het er als volgt uit:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **Het bovenstaande voorbeeld is de meest gangbare SPF TXT-record**. Deze record werkt voor bijna iedereen, ongeacht of uw Microsoft-datacenter zich in de Verenigde Staten of in Europa (inclusief Duitsland) of op een andere locatie bevindt.

   Als u echter Office 365 Duitsland hebt gekocht, onderdeel van Microsoft Cloud Duitsland, moet u de include-instructie van regel 4 gebruiken in plaats van regel 2. Als u bijvoorbeeld volledig gehost bent in Office 365 Duitsland (dat wil zeggen dat u geen on-premises-e-mailservers heeft) bevat uw SPF TXT-record rijen 1, 4 en 7 en ziet het er als volgt uit:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Als u al bent overgestapt naar Office 365 en uw SPF TXT-records hebt ingesteld voor uw aangepaste domein, en u migreert naar Office 365 Duitsland, moet u uw SPF TXT-record bijwerken. U kunt dit doen door `include:spf.protection.outlook.com` te wijzigen in `include:spf.protection.outlook.de`.

3. Zodra u uw SPF TXT-record hebt gemaakt, moet u het record in DNS bijwerken. **U kunt slechts één SPF TXT-record voor een domein hebben.** Als er een SPF TXT-record aanwezig is, moet u het bestaande record bijwerken, in plaats van een nieuwe record toe te voegen. Ga naar [DNS-records maken voor Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) en kies vervolgens de koppeling voor uw DNS-host.

4. De SPF TXT-record testen.

## <a name="how-to-handle-subdomains"></a>Subdomeinen verwerken

Het is belangrijk om te weten dat *u een afzonderlijke record moet maken voor elk subdomein, omdat subdomeinen niet de SPF-record van het topleveldomein overnemen*.

Voor elk domein en subdomein is een SPF-record met jokerteken (`*.`) nodig om te voorkomen dat aanvallers e-mail verzenden die afkomstig zou zijn van niet-bestaande subdomeinen. Bijvoorbeeld:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Problemen met SPF oplossen

Hebt u problemen met de SPF TXT-record? Lees [Probleemoplossing: aanbevolen procedures voor SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="what-does-spf-email-authentication-actually-do"></a>Wat doet SPF-e-mailverificatie eigenlijk?

Met SPF wordt bepaald welke e-mailservers namens u e-mail mogen verzenden. Kortom, SPF, DKIM, DMARC en andere technologieën die worden ondersteund door Office 365, helpen spoofing en phishing te voorkomen. SPF wordt toegevoegd als een TXT-record die door DNS wordt gebruikt om te bepalen welke e-mailservers e-mail kunnen verzenden namens uw aangepaste domein. De e-mailsystemen van de ontvanger raadplegen het SPF TXT-record om te bepalen of een bericht van uw aangepaste domein afkomstig is van een geautoriseerde berichtenserver.

Stel bijvoorbeeld dat uw aangepaste domein contoso.com gebruikmaakt van Office 365. U voegt een SPF TXT-record toe met de Office 365-berichtenservers als legitieme e-mailservers voor uw domein. Wanneer de ontvangende berichtenserver een bericht ontvangt van joe@contoso.com, zoekt de server het SPF TXT-record op voor contoso.com en controleert of het bericht geldig is. Als de ontvangende server heeft vastgesteld dat het bericht afkomstig is van een andere server dan de Office 365-berichtenservers die worden vermeld in de SPF-record, kan de ontvangende e-mailserver het bericht als spam weigeren.

Als uw aangepaste domein geen SPF TXT-record heeft, kunnen sommige ontvangende servers het bericht ook volledig weigeren. Dit komt omdat de ontvangende server niet kan valideren dat het bericht afkomstig is van een geautoriseerde berichtenserver.

Als u al e-mail hebt ingesteld voor Office 365, hebt u de berichtenservers van Microsoft al in DNS opgenomen als een SPF TXT-record. Er zijn echter enkele gevallen waarin u uw SPF TXT-record in DNS mogelijk moet bijwerken. Bijvoorbeeld:

- Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u SharePoint Online gebruikte. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. Werk de SPF TXT-record bij als u de opzoeklimiet van 10 bereikt en fouten ontvangt die het volgende melden: 'de opzoeklimiet is overschreden' en 'te veel hops'.

- Als u een hybride omgeving hebt met Office 365 en Exchange on-premises.

- U wilt DKIM en DMARC instellen (aanbevolen).

## <a name="more-information-about-spf"></a>Meer informatie over SPF

Zie [Hoe SPF werkt om spoofing en phishing in Office 365 te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks) voor geavanceerde voorbeelden, een meer gedetailleerde discussie over ondersteunde SPF-syntaxis, spoofing, probleemoplossing en hoe Office 365 SPF ondersteunt.

## <a name="next-steps-dkim-and-dmarc"></a>Volgende stappen: DKIM en DMARC

 SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt ingesteld, ook DKIM en DMARC voor Office 365 configureren.

Het doel van de e-mailverificatie van [DKIM](use-dkim-to-validate-outbound-email.md) is bewijzen dat er niet met de inhoud van het e-mailbericht is geknoeid.

Het doel van de e-mailverificatie van [DMARC](use-dmarc-to-validate-email.md) is ervoor te zorgen dat SPF- en DKIM-gegevens overeenkomen met het Van-adres.

 Zie [Hoe SPF werkt om spoofing en phishing in Office 365 te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks) voor geavanceerde voorbeelden, en een meer gedetailleerde discussie over ondersteunde SPF-syntaxis.

*Kies 'Deze pagina' onder 'Feedback' als u feedback over deze documentatie hebt.*
