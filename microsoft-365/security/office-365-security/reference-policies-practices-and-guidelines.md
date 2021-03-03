---
title: Naslagbeleid, procedures en richtlijnen
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
description: Microsoft heeft diverse beleidsregels en procedures ontwikkeld en verschillende best practices in de branche gebruikt om onze gebruikers te beschermen tegen aanstootgevende, ongewenste of schadelijke e-mail.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f53b1c36417b15e366b527dd1c12e4f23c06f632
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406594"
---
# <a name="reference-policies-practices-and-guidelines"></a>Verwijzing: Beleid, procedures en richtlijnen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft doet er alles aan om de meest vertrouwde gebruikerservaring op internet te bieden. Daarom heeft Microsoft verschillende beleidsregels en procedures ontwikkeld en verschillende best practices in de branche gebruikt om onze gebruikers te beschermen tegen aanstootgevende, ongewenste of schadelijke e-mail. Afzenders die e-mailberichten naar gebruikers verzenden, dienen er zeker van te zijn dat ze volledig begrijpen en de richtlijnen in dit artikel volgen om te helpen bij deze inspanning en mogelijke bezorgingsproblemen te helpen voorkomen.

Als u niet voldoet aan dit beleid en deze richtlijnen, kan ons ondersteuningsteam u mogelijk niet helpen. Als u zich houdt aan de richtlijnen, procedures en het beleid dat in dit artikel wordt beschreven en nog steeds bezorgingsproblemen ondervindt op basis van uw IP-adres, volgt u de stappen om een aanvraag voor het inzenden van berichten in te dienen. Zie De portal [delist gebruiken om uzelf](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)uit de lijst met geblokkeerde afzenders te verwijderen voor instructies.

## <a name="general-microsoft-policies"></a>Algemeen Microsoft-beleid

E-mail die naar Gebruikers van Microsoft 365 wordt verzonden, moet voldoen aan alle beleidsregels van Microsoft voor de verzending en het gebruik van e-mail van Microsoft 365.

- De servicesvoorwaarden die van toepassing zijn op Microsoft 365; met name het verbieden van het gebruik van de service voor spam of het verspreiden van malware.

- [Microsoft-servicesovereenkomst](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Overheidsvoorschriften

E-mail die naar Microsoft 365-gebruikers wordt verzonden, moet voldoen aan alle toepasselijke wetten en voorschriften die van toepassing zijn op e-mailcommunicatie in de toepasselijke jurisdictie.

- [CAN-SPAM Act: een nalevingshandleiding voor bedrijven](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [Reacties en verantwoordelijkheden 'Mij verwijderen': E-mail marketeers moeten claims 'Afmelden' voldoen](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Technische richtlijnen

E-mail die naar Microsoft 365 wordt verzonden, moet voldoen aan de toepasselijke aanbevelingen in de onderstaande documenten (sommige koppelingen zijn alleen beschikbaar in het Engels).

- [RFC 2505: Antispamaanbevelingen voor SMTP-MTA's](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-serviceuitbreiding voor opdracht pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Bovendien moeten e-mailservers die verbinding maken met Microsoft 365, voldoen aan de volgende vereisten:

- Van de afzender wordt verwacht dat hij voldoet aan alle technische standaarden voor de verzending van internet-e-mail, zoals gepubliceerd door Internet Engineering Task Force (IETF), inclusief RFC 5321, RFC 5322 en andere.

- Nadat een numerieke SMTP-foutreactiecode tussen 500 en 599 (ook wel een permanente reactie op niet-bezorging of NDR genoemd) is opgegeven, mag de afzender niet proberen dat bericht opnieuw naar die geadresseerde te verzenden.

- Na meerdere niet-bezorgingsreacties moet de afzender niet langer proberen e-mailberichten naar die geadresseerde te verzenden.

- Berichten mogen niet worden verzonden via onveilige e-mailrelais of proxyservers.

- Het mechanisme voor het afmelden van een abonnement op afzonderlijke lijsten of alle lijsten die worden gehost door de afzender, moet duidelijk worden beschreven en gemakkelijk te vinden en te gebruiken voor ontvangers.

- Verbindingen vanuit een dynamische IP-ruimte worden mogelijk niet geaccepteerd.

- E-mailservers moeten geldige reverse-DNS-records hebben.

## <a name="reputation-management"></a>Reputatiebeheer

Afzenders, internetproviders en andere serviceproviders moeten actief de reputatie van uw uitgaande IP-adressen beheren.

## <a name="microsoft-365-limits"></a>Microsoft 365-limieten

Afzenders moeten voldoen aan de Microsoft 365-limieten die worden vermeld in [Exchange Online Protection-limieten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>Informatiebronnen en organisaties voor e-mailbezorging

Microsoft werkt actief samen met brancheorganisaties en serviceproviders om het internet- en e-mailsysteem te verbeteren. Deze organisaties hebben best practice-documenten gepubliceerd die we ondersteunen en die worden aanbevolen dat afzenders zich houden aan. Dit verbetert de mogelijkheid om e-mail te verzenden tussen verschillende e-mailproviders over de hele wereld.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [Afzender van e& mailprovider](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Rapportage van misbruik en spam

Zie Berichten en bestanden rapporteren aan Microsoft voor informatie over het melden van onwettige, aanstootgevende, ongewenste of [schadelijke e-mail.](report-junk-email-messages-to-microsoft.md) Het verzenden van deze typen communicatie is een schending van het Microsoft-beleid en er wordt passende actie ondernomen op bevestigd rapporten.

## <a name="law-enforcement"></a>Advocatenkantoor

Als u lid bent van de juridische procedure en u microsoft Corporation wilt helpen met juridische documentatie met betrekking tot Office 365, of als u vragen hebt met betrekking tot juridische documentatie die u bij Microsoft hebt ingediend, belt u (1) (425) 722-1299.
