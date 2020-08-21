---
title: Naslag beleid, procedures en richtlijnen
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
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft heeft verschillende beleidsregels en procedures ontwikkeld en u hebt diverse best practices ontwikkeld om onze gebruikers te helpen beschermen tegen beledigende, ongewenste e-mail of kwaadaardige e-mail.
ms.openlocfilehash: 13bc62f8be25a21f5ed2d1c2c2f4208a56d28bf0
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826515"
---
# <a name="reference-policies-practices-and-guidelines"></a>Verwijzing: Beleid, procedures en richtlijnen

Microsoft is specifiek bedoeld om u te helpen de meest vertrouwde gebruikerservaring op internet te bieden. Microsoft heeft daarom verschillende beleidsregels en procedures ontwikkeld en diverse best practices voor onze bedrijfstak ontwikkeld om onze gebruikers te helpen beschermen tegen beledigende, ongewenste e-mail of kwaadaardige e-mail. Af te leveren afzenders die een e-mailbericht naar gebruikers proberen te verzenden, moeten ze volledig begrijpen en voldoen aan de hand van de instructies in dit artikel om potentiële problemen met de bezorging te voorkomen.

Als u niet voldoet aan deze beleidsregels en richtlijnen, is het mogelijk dat ons ondersteuningsteam u mogelijk niet helpt. Als u voldoet aan de richtlijnen, werkwijzen en beleidsregels die worden weergegeven in dit artikel en nog steeds afleverings problemen ondervinden op basis van uw verzendende IP-adres, volgt u de stappen om een aanvraag voor een aanvraag in te dienen. Voor instructies raadpleegt u [de lijst met geblokkeerde afzenders gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Algemeen Microsoft-beleid

E-mail die wordt verzonden naar Microsoft 365-gebruikers moet voldoen aan alle Microsoft-beleidsregels voor het verzenden van e-mail en het gebruik van Microsoft 365.

- De Servicevoorwaarden van Microsoft 365; met name het verbod tegen het gebruik van de service voor spam of het distribueren van malware.

- [Serviceovereenkomst van Microsoft](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Regerings voorschriften

E-mail verzonden naar Microsoft 365-gebruikers moeten voldoen aan alle toepasselijke wetten en voorschriften met betrekking tot e-mail communicatie in de toepasselijke jurisdictie.

- [CAN-SPAM Act: een compliance-handleiding voor bedrijven](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Verwijder mij de reacties en verantwoordelijkheden: e-mailmarketingers moeten de claim" Afmelden "melden](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Technische richtlijnen

E-mail die naar Microsoft 365 is verzonden, moet voldoen aan de toepasselijke aanbevelingen die worden vermeld in de onderstaande documenten (sommige koppelingen zijn alleen beschikbaar in het Engels).

- [RFC 2505: aanbevelingen van anti spam voor SMTP-MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP-service-uitbreiding voor opdracht pipeline](https://www.ietf.org/rfc/rfc2920.txt)

Daarnaast moeten e-mailservers die verbinding maken met Microsoft 365, voldoen aan de volgende vereisten:

- Verzenders wordt geacht te voldoen aan alle technische normen voor de verzending van Internet-e-mailberichten, zoals deze is gepubliceerd door de Internet Engineering Task Force van de Internet maatschappij, waaronder RFC 5321, RFC 5322 en andere.

- Nadat een numerieke antwoordcode voor SMTP-fout is opgegeven tussen 500 en 599 (ook wel een permanente niet-bezorg antwoord of NDR genoemd), moet de afzender dat bericht niet meer proberen te verzenden naar die geadresseerde.

- Na meerdere niet-bezorgings reacties moet de afzender de nieuwe pogingen voor het verzenden van e-mail naar die geadresseerde beëindigen.

- Berichten mogen niet worden verzonden via Inveilige e-mail relay of proxyservers.

- Het mechanisme voor het opzeggen van een abonnement op basis van aparte lijsten of lijsten die worden gehost door de afzender, moet duidelijk duidelijk gedocumenteerd en gemakkelijk te vinden zijn.

- Verbindingen via dynamische IP-ruimte worden mogelijk niet geaccepteerd.

- De e-mailservers moeten geldige DNS-records met wederinkoop hebben.

## <a name="reputation-management"></a>Reputatie beheer

Voor afzenders, providers en andere service providers moet de reputatie van uw uitgaande IP-adressen actief worden beheerd.

## <a name="microsoft-365-limits"></a>Limieten voor Microsoft 365

Afzenders moeten voldoen aan beperkingen voor Microsoft 365 die worden vermeld in [Exchange Online Protection-beperkingen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Bronnen voor het leveren van e-mail en organisaties

Microsoft werkt actief met bedrijfstak en service providers om de Internet-en e-mail ecosystem te verbeteren. Deze organisaties hebben de beste Oefen documenten gepubliceerd waarmee we afzenders kunnen best practices. Hierdoor kunt u e-mail van diverse e-mail providers overal ter wereld verzorgt.

- [Chatberichten via een mobiele anti-malware](https://www.m3aawg.org/)

- [Online vertrouwens Alliantie](https://www.otalliance.org/resources)

- [E-mail afzender & provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Misbruik en spam rapporten

Als u onwettige, beledigende, ongewenste of schadelijke e-mail wilt rapporteren, raadpleegt [u berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md). Het verzenden van deze communicatietypen verloopt een schending van Microsoft-beleid en de juiste actie wordt uitgevoerd op bevestigde rapporten.

## <a name="law-enforcement"></a>Naleving van de regelgeving

Als u lid bent van de wet enforcement en Microsoft Corporation met juridische documentatie met Office 365, of als u vragen hebt over juridische documentatie die u bij Microsoft hebt ingediend, kunt u bellen (1) (425) 722-1299.
