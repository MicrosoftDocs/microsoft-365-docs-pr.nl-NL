---
title: SPF instellen om adresvervalsing te helpen voorkomen
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u een DNS-record (Domain Name Service) bijwerkt, zodat u SPF (Sender Policy Framework) kunt gebruiken met uw aangepaste domein in Office 365.
ms.openlocfilehash: 6061cd9ea52f4ed4073f510dcba60fba9b4fd23c
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588074"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>SPF instellen om adresvervalsing te helpen voorkomen

 **Overzicht:** in dit artikel wordt beschreven hoe u een DNS-record (Domain Name Service) bijwerkt, zodat u SPF (Sender Policy Framework) kunt gebruiken met uw aangepaste domein in Office 365. Het gebruik van SPF helpt bij het valideren van uitgaande e-mail die is verzonden vanuit uw aangepaste domein.

Om een aangepast domein te gebruiken, vereist Office 365 dat u een Sender Policy Framework (SPF) TXT-record toevoegt aan uw DNS-record om spoofing te helpen voorkomen. Met SPF wordt bepaald welke e-mailservers namens u e-mail mogen verzenden. Kortom, SPF, DKIM, DMARC en andere technologieën die worden ondersteund door Office 365, helpen spoofing en phishing te voorkomen. SPF wordt toegevoegd als een TXT-record die door DNS wordt gebruikt om te bepalen welke e-mailservers e-mail kunnen verzenden namens uw aangepaste domein. De e-mailsystemen van de ontvanger raadplegen het SPF TXT-record om te bepalen of een bericht van uw aangepaste domein afkomstig is van een geautoriseerde berichtenserver.

Stel bijvoorbeeld dat uw aangepaste domein contoso.com gebruikmaakt van Office 365. U voegt een SPF TXT-record toe met de Office 365-berichtenservers als legitieme e-mailservers voor uw domein. Wanneer de ontvangende berichtenserver een bericht ontvangt van joe@contoso.com, zoekt de server het SPF TXT-record op voor contoso.com en controleert of het bericht geldig is. Als de ontvangende server heeft vastgesteld dat het bericht afkomstig is van een andere server dan de Office 365-berichtenservers die worden vermeld in de SPF-record, kan de ontvangende e-mailserver het bericht als spam weigeren.

Als uw aangepaste domein geen SPF TXT-record heeft, kunnen sommige ontvangende servers het bericht ook volledig weigeren. Dit komt omdat de ontvangende server niet kan valideren dat het bericht afkomstig is van een geautoriseerde berichtenserver.

Als u al e-mail hebt ingesteld voor Office 365, hebt u de berichtenservers van Microsoft al in DNS opgenomen als een SPF TXT-record. Er zijn echter enkele gevallen waarin u uw SPF TXT-record in DNS mogelijk moet bijwerken. Bijvoorbeeld:

- Voorheen moest u een andere SPF TXT-record toevoegen aan uw aangepaste domein als u SharePoint Online gebruikte. Dit is niet meer nodig. Deze wijziging moet het risico verkleinen dat SharePoint Online-meldingsberichten in de map Ongewenste e-mail terechtkomen. Werk de SPF TXT-record bij als u de opzoeklimiet van 10 bereikt en fouten ontvangt die het volgende melden: 'de opzoeklimiet is overschreden' en 'te veel hops'.

- Als u een hybride omgeving hebt met Office 365 en Exchange on-premises.

- U wilt DKIM en DMARC instellen (aanbevolen).

## <a name="updating-your-spf-txt-record-for-office-365"></a>De SPF TXT-record voor Office 365 bijwerken

Voordat u de TXT-record in DNS bijwerkt, moet u enkele gegevens verzamelen en de indeling van het record bepalen. Hierdoor voorkomt u dat er DNS-fouten worden gegenereerd. Zie [Hoe SPF werkt om spoofing en phishing in Office 365 te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks) voor geavanceerde voorbeelden, en een meer gedetailleerde discussie over ondersteunde SPF-syntaxis.

Verzamel de volgende informatie:

- Het huidige SPF TXT-record voor uw aangepaste domein. Zie [De informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)voor instructies.

- Externe IP-adressen van alle on-premises messaging-servers. Bijvoorbeeld: **131.107.2.200**.

- Domeinnamen die moeten worden gebruikt voor alle domeinen van derden die u wilt opnemen in het SPF TXT-record. Sommige aanbieders van bulkmail hebben subdomeinen ingesteld voor gebruik door hun klanten. Het bedrijf MailChimp heeft bijvoorbeeld **servers.mcsv.net** opgezet.

- Bepaal welke handhavingsregel u wilt gebruiken voor uw SPF TXT-record. We adviseren **-alle**. Zie voor meer informatie over andere syntaxisopties [SPF TXT-record syntaxis voor Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>De SPF TXT-record toevoegen of bijwerken

1. Ga na of u bekend bent met de SFP-syntaxis in de volgende tabel.

   ||**Als u werkt met...**|**Gangbaar bij klanten?**|**Voegt u deze toe...**|
   |:-----|:-----|:-----|:-----|
   |1|Elk e-mailsysteem (vereist)|Gangbaar. Alle SPF-records beginnen met deze waarde|v=spf1|
   |2|Exchange Online|Gangbaar|include:spf.protection.outlook.com|
   |3|Alleen Exchange Online|Niet gangbaar|ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com|
   |4|Office 365 Duitsland, alleen Microsoft Cloud Duitsland|Niet gangbaar|include:spf.protection.outlook.de|
   |5|E-mailsysteem van derden|Niet gangbaar|inclusief:\<domain name\>  <br/> Waarbij domeinnaam de domeinnaam is van het e-mailsysteem van derden.|
   |6|On-premises e-mailsysteem. Bijvoorbeeld, Exchange Online Protection plus een ander e-mailsysteem|Niet gangbaar| Gebruik een van deze voor elk extra e-mailsysteem: <br> ip4:\<_IP address_\>  <br/>  ip6:\<_IP address_\>  <br/>  inclusief:\<_domain name_\>  <br/>  Waar de waarde voor \<_IP address_\> het IP-adres van het andere e-mailsysteem is en \<_domain name_\> de domeinnaam is van het andere e-mailsysteem waarmee e-mail wordt verzonden namens uw domein.|
   |7|Elk e-mailsysteem (vereist)|Gangbaar. Alle SPF-records eindigen met deze waarde|\<_enforcement rule_\>  <br/> Dit kan een van meerdere waarden zijn. We adviseren u om **-alle**te gebruiken.|

2. Als u dit nog niet hebt gedaan, kunt u het SPF TXT-record maken met behulp van de syntaxis uit de tabel:

   Als u bijvoorbeeld volledig gehost bent in Office 365, dat wil zeggen dat u geen on-premises e-mailservers heeft, bevat uw SPF TXT-record rijen 1, 2 en 7 en ziet het er als volgt uit:

   `v=spf1 include:spf.protection.outlook.com -all`

   Dit is de meest gangbare TXT-record voor SPF. Deze record werkt voor bijna iedereen, ongeacht of uw Microsoft-datacenter zich in de Verenigde Staten of in Europa (inclusief Duitsland) of op een andere locatie bevindt.

   Als u echter Office 365 Duitsland hebt gekocht, onderdeel van Microsoft Cloud Duitsland, moet u de include-instructie van regel 4 gebruiken in plaats van regel 2. Als u bijvoorbeeld volledig gehost bent in Office 365 Duitsland, dat wil zeggen dat u geen lokale e-mailservers heeft, bevat uw SPF TXT-record rijen 1, 4 en 7 en ziet het er als volgt uit:

   `v=spf1 include:spf.protection.outlook.de -all`

   Als u al bent overgestapt naar Office 365 en uw SPF TXT-records hebt ingesteld voor uw aangepaste domein, en u migreert naar Office 365 Duitsland, moet u uw SPF TXT-record bijwerken. Als u dit wilt doen, wijzigt u **include:spf.protection.outlook.com** naar **include:spf.protection.outlook.de**.

3. Zodra u uw SPF TXT-record hebt gemaakt, moet u het record in DNS bijwerken. U kunt slechts één SPF TXT-record voor een domein hebben. Als er een SPF TXT-record aanwezig is, moet u het bestaande record bijwerken, in plaats van een nieuwe record toe te voegen. Ga naar [DNS-records maken voor Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) en klik vervolgens op de link voor uw DNS-host.

4. De SPF TXT-record testen.

## <a name="more-information-about-spf"></a>Meer informatie over SPF

Zie [Hoe SPF werkt om spoofing en phishing in Office 365 te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks) voor geavanceerde voorbeelden, een meer gedetailleerde discussie over ondersteunde SPF-syntaxis, spoofing, probleemoplossing en hoe Office 365 SPF ondersteunt.

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Volgende stappen: nadat u SPF hebt ingesteld voor Office 365

Hebt u problemen met de SPF TXT-record? Lees [Probleemoplossing: aanbevolen procedures voor SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

 SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Office 365 configureren. Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md). Zie vervolgens [DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md).
