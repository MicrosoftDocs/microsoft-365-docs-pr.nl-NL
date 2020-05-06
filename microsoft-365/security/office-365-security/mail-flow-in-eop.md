---
title: E-mailstroom in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: In dit artikel kunnen Exchange Online Protection (EOP) klanten meer te weten komen over het configureren van aangepaste e-mailroutering die mogelijk voldoet aan hun zakelijke vereisten.
ms.openlocfilehash: cdc919c628f2254ffc971678f7887c37786d2528
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034230"
---
# <a name="mail-flow-in-eop"></a>E-mailstroom in EOP

Als Exchange Online Protection (EOP)-klant gaan alle berichten die naar uw organisatie worden verzonden via EOP voordat uw werknemers ze zien. Of u nu al uw postvakken in de cloud host met Exchange Online, of uw postvakken op locatie host (een zelfstandig scenario genoemd), misschien om gebruik te blijven maken van uw bestaande infrastructuur, u hebt opties over hoe u berichten routeren die door EOP worden verzonden voor verwerking voordat ze worden doorgestuurd naar de inboxen van uw werknemer.

U aangepaste e-mailroutering configureren om aan uw berichten te voldoen aan een zakelijke vereisten. U bijvoorbeeld al uw uitgaande e-mail doorgeven via een beleidsfilterapparaat.

## <a name="working-with-messages-and-message-access-options"></a>Werken met berichten en opties voor berichttoegang

EOP biedt veel flexibiliteit in de manier waarop uw berichten worden doorgestuurd. In de volgende onderwerpen worden stappen in het e-mailstroomproces uitgelegd.

[Directory based edge blocking gebruiken om berichten die naar ongeldige ontvangers worden verzonden, af te wijzen](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Directory Based Edge Blocking waarmee u berichten weigeren voor ongeldige ontvangers in de perimeter van het servicenetwerk.

[Beheerde domeinen weergeven of bewerken in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschrijft hoe u domeinen beheert die zijn gekoppeld aan uw EOP-service.

Als u subdomeinen aan uw organisatie toevoegt, kan uw EOP-service u ook helpen deze te beheren. Meer informatie over subdomeinen bij [E-mailstroom inschakelen voor subdomeinen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configureer e-mailstroom met behulp van connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceert connectors en laat zien hoe u ze gebruiken om e-mailroutering aan te passen. Scenario's omvatten het waarborgen van veilige communicatie met een partnerorganisatie en het opzetten van een slimme host.

Als u ervoor wilt zorgen dat ongewenste e-mail correct wordt doorgestuurd naar de map met ongewenste e-mail van elke gebruiker, moet u een paar configuratiestappen uitvoeren. Deze worden beschreven in [Standalone EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Als u geen berichten naar de map met ongewenste e-mail van elke gebruiker wilt verplaatsen, u een andere actie kiezen door uw inhoudsfilterbeleid te bewerken in het Exchange-beheercentrum. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="verify-mail-flow"></a>E-mailstroom verifiëren

Zie de 'Hoe weet je dat deze taak heeft gewerkt', inclusief je connectorconfiguratie, om te controleren of je eop-setup, inclusief je connectorconfiguratie, goed werkt. sectie in [Uw EOP-service instellen](set-up-your-eop-service.md).

[Test de e-mailstroom door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) en geeft instructies voor het testen dat uw e-mailstroom correct is ingesteld.
