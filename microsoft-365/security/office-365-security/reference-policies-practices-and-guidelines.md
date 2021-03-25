---
title: Referentiebeleid, procedures en richtlijnen
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
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft heeft verschillende beleidsregels, procedures en verschillende best practices voor de industrie ontwikkeld om onze gebruikers te beschermen tegen misbruik, ongewenste of schadelijke e-mail.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1a71b891829a2c9ea31502342c855db4126a6b5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204340"
---
# <a name="reference-policies-practices-and-guidelines"></a>Verwijzing: Beleid, procedures en richtlijnen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft is er alles aan doen om de meest vertrouwde gebruikerservaring op het web te bieden. Daarom heeft Microsoft verschillende beleidsregels, procedures en verschillende best practices voor de industrie ontwikkeld om onze gebruikers te beschermen tegen ongewenste of schadelijke e-mail. Afzenders die e-mail naar gebruikers proberen te verzenden, moeten ervoor zorgen dat ze de richtlijnen in dit artikel volledig begrijpen en volgen om te helpen bij deze inspanning en om mogelijke bezorgingsproblemen te voorkomen.

Als u niet voldoet aan deze beleidsregels en richtlijnen, is het mogelijk dat ons ondersteuningsteam u niet kan helpen. Als u zich houdt aan de richtlijnen, procedures en beleidsregels die in dit artikel worden gepresenteerd en nog steeds bezorgingsproblemen ondervindt op basis van uw verzendende IP-adres, volgt u de stappen om een aanvraag voor het op de lijst zetten in te dienen. Zie De portal van de lijst verwijderen om uzelf te verwijderen uit de lijst met [geblokkeerde afzenders](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)voor instructies.

## <a name="general-microsoft-policies"></a>Algemeen Microsoft-beleid

E-mail die naar Microsoft 365-gebruikers wordt verzonden, moet voldoen aan alle Microsoft-beleidsregels voor het verzenden van e-mail en het gebruik van Microsoft 365.

- Servicesvoorwaarden die van toepassing zijn op Microsoft 365; in het bijzonder het verbod op het gebruik van de service voor spam of het distribueren van malware.

- [Microsoft Services-overeenkomst](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Overheidsvoorschriften

E-mail die naar Microsoft 365-gebruikers wordt verzonden, moet voldoen aan alle toepasselijke wetten en voorschriften voor e-mailcommunicatie in de toepasselijke jurisdictie.

- [CAN-SPAM Act: A Compliance Guide for Business](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [Antwoorden en verantwoordelijkheden 'Mij verwijderen': E-mail marketeers moeten 'Afmelden' claims honoreren](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Technische richtlijnen

E-mail die naar Microsoft 365 wordt verzonden, moet voldoen aan de toepasselijke aanbevelingen die in de onderstaande documenten worden vermeld (sommige koppelingen zijn alleen beschikbaar in het Engels).

- [RFC 2505: Aanbevelingen voor antispam voor SMTP-MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-serviceextensie voor command pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Daarnaast moeten e-mailservers die verbinding maken met Microsoft 365 voldoen aan de volgende vereisten:

- De afzender voldoet naar verwachting aan alle technische standaarden voor het verzenden van internet-e-mail, zoals gepubliceerd door de Internet Engineering Task Force (IETF) van de internetmaatschappij, waaronder RFC 5321, RFC 5322 en andere.

- Nadat de afzender een numerieke SMTP-foutresponscode tussen 500 en 599 heeft gegeven (ook wel een permanente reactie op niet-bezorging of NDR genoemd), mag de afzender niet proberen dit bericht opnieuw door te sturen naar die geadresseerde.

- Na meerdere reacties zonder bezorging moet de afzender verdere pogingen om e-mail naar die geadresseerde te verzenden, staken.

- Berichten mogen niet worden verzonden via onveilige e-mail relay- of proxyservers.

- Het mechanisme voor het afmelden, van afzonderlijke lijsten of alle lijsten die door de afzender worden gehost, moet duidelijk zijn gedocumenteerd en gemakkelijk voor geadresseerden om ze te vinden en te gebruiken.

- Verbindingen vanuit dynamische IP-ruimte worden mogelijk niet geaccepteerd.

- E-mailservers moeten geldige reverse DNS-records hebben.

## <a name="reputation-management"></a>Reputatiebeheer

Afzenders, internetproviders en andere serviceproviders moeten de reputatie van uw uitgaande IP-adressen actief beheren.

## <a name="microsoft-365-limits"></a>Microsoft 365-limieten

Afzenders moeten zich houden aan Microsoft 365-limieten die worden vermeld in [Exchange Online Protection Limits.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>E-mailbezorgingsbronnen en -organisaties

Microsoft werkt actief samen met brancheorganisaties en serviceproviders om het internet- en e-mailecosysteem te verbeteren. Deze organisaties hebben best practice-documenten gepubliceerd die we ondersteunen en waar afzenders zich aan houden. Dit verbetert uw mogelijkheid om e-mail te leveren bij verschillende e-mailserviceproviders over de hele wereld.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [E-mail afzender & providerCoalitie](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Misbruik en spamrapportage

Zie Berichten en bestanden rapporteren aan Microsoft als u onrechtmatige, onrechtmatige, ongewenste of schadelijke e-mail [wilt rapporteren.](report-junk-email-messages-to-microsoft.md) Het verzenden van dit type communicatie is een schending van het Microsoft-beleid en de juiste actie wordt ondernomen op bevestigd rapporten.

## <a name="law-enforcement"></a>Rechtshandhaving

Als u lid bent van de wetshandhaving en Microsoft Corporation wilt dienen met juridische documentatie over Office 365 of als u vragen hebt over juridische documentatie die u hebt ingediend bij Microsoft, kunt u bellen met (1) (425) 722-1299.