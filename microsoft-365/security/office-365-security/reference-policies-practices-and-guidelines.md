---
title: Referentiebeleid, -praktijken en -richtlijnen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft heeft verschillende beleidsregels, procedures ontwikkeld en verschillende best practices in de branche aangenomen om onze gebruikers te beschermen tegen beledigende, ongewenste of schadelijke e-mail.
ms.openlocfilehash: 6e73355c02e0416a80441aff8143fcbf51150b94
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634386"
---
# <a name="reference-policies-practices-and-guidelines"></a>Verwijzing: Beleid, procedures en richtlijnen

Microsoft is toegewijd om te helpen de meest vertrouwde gebruikerservaring op het web te bieden. Daarom heeft Microsoft verschillende beleidsregels, procedures ontwikkeld en verschillende best practices in de branche aangenomen om onze gebruikers te beschermen tegen beledigende, ongewenste of schadelijke e-mail. Afzenders die e-mail naar gebruikers proberen te sturen, moeten ervoor zorgen dat ze de richtlijnen in dit artikel volledig begrijpen en volgen om te helpen bij deze inspanning en om mogelijke leveringsproblemen te voorkomen.

Als u zich niet aan deze beleidsregels en richtlijnen houdt, is het mogelijk dat ons ondersteuningsteam u niet kan helpen. Als u zich houdt aan de richtlijnen, praktijken en beleidsregels die in dit artikel worden gepresenteerd en nog steeds problemen met de weergave ondervindt op basis van uw verzendende IP-adres, volgt u de stappen om een verzoek tot schrapping in te dienen. Zie De [lijstportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)voor instructies.

## <a name="general-microsoft-policies"></a>Algemeen Microsoft-beleid

E-mail die naar Microsoft 365-gebruikers wordt verzonden, moet voldoen aan alle Microsoft-beleidsregels met betrekking tot e-mailoverdracht en -gebruik van Office 365.

- Servicevoorwaarden voor Office 365; in het bijzonder, het verbod op het gebruik van de dienst om spam of verspreiden van malware

- [Microsoft Services-overeenkomst](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Overheidsvoorschriften

E-mail die naar Microsoft 365-gebruikers wordt verzonden, moet voldoen aan alle toepasselijke wet- en regelgeving voor e-mailcommunicatie in het toepasselijke rechtsgebied.

- [CAN-SPAM Act: een compliance gids voor bedrijven](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Verwijder me" reacties en verantwoordelijkheden: E-mail marketeers moeten honor "Unsubscribe" Claims](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Technische richtlijnen

E-mail die naar Microsoft 365 wordt verzonden, moet voldoen aan de toepasselijke aanbevelingen in de onderstaande documenten (sommige links zijn alleen beschikbaar in het Engels).

- [RFC 2505: Anti-Spam Aanbevelingen voor SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-serviceextensie voor command pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Bovendien moeten e-mailservers die verbinding maken met Microsoft 365 voldoen aan de volgende vereisten:

- Afzender zal naar verwachting voldoen aan alle technische normen voor de overdracht van internet e-mail, zoals gepubliceerd door The Internet Society's Internet Engineering Task Force (IETF), met inbegrip van RFC 5321, RFC 5322, en anderen.

- Nadat de afzender een numerieke SMTP-foutreactiecode tussen 500 en 599 heeft gegeven (ook wel een permanent niet-leveringsantwoord of NDR genoemd), mag de afzender niet proberen dat bericht opnieuw naar die ontvanger te verzenden.

- Na meerdere reacties zonder levering moet de afzender verdere pogingen om e-mail naar die ontvanger te verzenden, staken.

- Berichten mogen niet worden verzonden via onveilige e-mailrelay- of proxyservers.

- Het mechanisme voor uitschrijven, hetzij van individuele lijsten of alle lijsten gehost door de afzender, moet duidelijk worden gedocumenteerd en gemakkelijk te vinden en te gebruiken.

- Verbindingen vanuit dynamische IP-ruimte worden mogelijk niet geaccepteerd.

- E-mailservers moeten beschikken over geldige reverse DNS-records.

## <a name="reputation-management"></a>Reputatiemanagement

Afzenders, ISP's en andere serviceproviders moeten actief de reputatie van uw uitgaande IP-adressen beheren.

## <a name="microsoft-365-limits"></a>Microsoft 365-limieten

Afzenders moeten zich houden aan microsoft 365-limieten die worden vermeld in [exchange online-beveiligingslimieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Bronnen en organisaties voor e-mailbezorging

Microsoft werkt actief samen met brancheorganisaties en serviceproviders om het internet- en e-mailecosysteem te verbeteren. Deze organisaties hebben best practice-documenten gepubliceerd die we ondersteunen en aanbevelen aan afzenders. Dit verbetert uw vermogen om e-mail te leveren bij verschillende e-mailserviceproviders over de hele wereld.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online vertrouwensalliantie](https://www.otalliance.org/resources)

- [Coalitie &amp; van afzenderprovider e-mail](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Meldingen van misbruik en spam

Zie Berichten en bestanden rapporteren aan [Microsoft](report-junk-email-messages-to-microsoft.md)om onwettige, beledigende, ongewenste of schadelijke e-mail te melden. Het verzenden van dit soort berichten is een schending van het Microsoft-beleid en er wordt passende actie ondernomen op basis van bevestigde rapporten.

## <a name="law-enforcement"></a>Rechtshandhaving

Als u lid bent van de rechtshandhaving en Microsoft Corporation wilt voorzien van juridische documentatie met betrekking tot Office 365, of als u vragen heeft over juridische documentatie die u bij Microsoft hebt ingediend, bel dan (1) (425) 722-1299.
