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
ms.openlocfilehash: e6e5565b032af656b2204ce448581014595013de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808795"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referentie: Beleid, praktijken en richtlijnen

Microsoft is toegewijd aan het helpen bieden van de meest vertrouwde gebruikerservaring op het web. Daarom heeft Microsoft verschillende beleidsregels, procedures ontwikkeld en verschillende best practices in de branche aangenomen om onze gebruikers te beschermen tegen beledigende, ongewenste of schadelijke e-mail. Afzenders die e-mail naar Office 365-gebruikers proberen te verzenden, moeten ervoor zorgen dat ze het volledig begrijpen en volgen de richtlijnen in dit artikel om te helpen bij deze inspanning en om mogelijke leveringsproblemen te voorkomen.

Als u niet voldoet aan dit beleid en richtlijnen, is het mogelijk dat ons ondersteuningsteam u niet helpt. Als u zich houdt aan de richtlijnen, praktijken en beleidsregels die in dit artikel worden gepresenteerd en nog steeds leveringsproblemen ondervinden op basis van uw ip-adres, volgt u de stappen om een aanvraag voor het verwijderen in te dienen. Zie De [lijstportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Office 365 te verwijderen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)voor instructies.

## <a name="general-microsoft-policies"></a>Algemeen Microsoft-beleid

E-mail die naar Office 365-gebruikers wordt verzonden, moet voldoen aan alle Microsoft-beleidsregels voor e-mailverzending en -gebruik van Office 365.

- Servicevoorwaarden die van toepassing zijn op Office 365; in het bijzonder het verbod op het gebruik van de dienst om spam te verspreiden of malware te verspreiden

- [Microsoft Services-overeenkomst](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Overheidsvoorschriften

E-mail die naar Office 365-gebruikers wordt verzonden, moet zich houden aan alle toepasselijke wet- en regelgeving voor e-mailcommunicatie in het toepasselijke rechtsgebied.

- [CAN-SPAM Act: Een compliance gids voor bedrijven](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Verwijder mij" reacties en verantwoordelijkheden: E-mail marketeers moeten honor "Unsubscribe" Claims](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Technische richtlijnen

E-mail die naar Office 365 wordt verzonden, moet voldoen aan de toepasselijke aanbevelingen in de onderstaande documenten (sommige koppelingen zijn alleen beschikbaar in het Engels).

- [RFC 2505: Anti-Spam Aanbevelingen voor SMTP MTA's](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-serviceuitbreiding voor command pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Bovendien moeten e-mailservers die verbinding maken met Office 365 voldoen aan de volgende vereisten:

- Afzender zal naar verwachting voldoen aan alle technische normen voor de transmissie van internet e-mail, zoals gepubliceerd door The Internet Society's Internet Engineering Task Force (IETF), waaronder RFC 5321, RFC 5322, en anderen.

- Nadat hij tussen 500 en 599 een numerieke SMTP-foutreactiecode heeft gegeven (ook wel een permanente niet-leveringsreactie of NDR genoemd), mag de afzender niet proberen dat bericht opnieuw naar die ontvanger te verzenden.

- Na meerdere niet-bezorgingsreacties moet de afzender verdere pogingen om e-mail naar die ontvanger te verzenden staken.

- Berichten mogen niet worden verzonden via onveilige e-mailrelay- of proxyservers.

- Het mechanisme voor het uitschrijven, hetzij uit afzonderlijke lijsten of alle lijsten die door de afzender worden gehost, moet duidelijk gedocumenteerd en gemakkelijk zijn voor ontvangers om te vinden en te gebruiken.

- Verbindingen uit dynamische IP-ruimte worden mogelijk niet geaccepteerd.

- E-mailservers moeten beschikken over geldige omgekeerde DNS-records.

## <a name="reputation-management"></a>Reputatiemanagement

Afzenders, ISP's en andere serviceproviders moeten actief de reputatie van uw uitgaande IP-adressen beheren.

## <a name="office-365-limits"></a>Office 365-limieten

Afzenders moeten zich houden aan Office 365-limieten die zijn vermeld in [Exchange Online Protection Limits.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>Bronnen en organisaties voor e-mailbezorging

Microsoft werkt actief samen met brancheorganisaties en serviceproviders om het internet- en e-mailecosysteem te verbeteren. Deze organisaties hebben best practice documenten gepubliceerd die we ondersteunen en aanbevelen afzenders zich aan te houden. Dit verbetert uw vermogen om e-mail te leveren onder verschillende e-mailserviceproviders over de hele wereld.

- [Messaging Malware Mobile Anti-Abuse Werkgroep](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Coalitie &amp; voor afzender se-mail](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Misbruik en spamrapportage

Als u onwettige, beledigende, ongewenste of schadelijke e-mail wilt melden, u [ongewenste e-mail en phishing melden in het web van Outlook.](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) Het verzenden van dit soort berichten is een schending van het Microsoft-beleid en er zullen passende maatregelen worden genomen op basis van bevestigde rapporten.

## <a name="law-enforcement"></a>Rechtshandhaving

Als u lid bent van de rechtshandhaving en Microsoft Corporation wilt dienen met juridische documentatie met betrekking tot Office 365, of als u vragen hebt over juridische documentatie die u bij Microsoft hebt ingediend, belt u (1) (425) 722-1299.
