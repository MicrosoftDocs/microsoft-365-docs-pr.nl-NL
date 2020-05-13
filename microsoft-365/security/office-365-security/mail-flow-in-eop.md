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
description: Beheerder kan meer informatie krijgen over de opties voor het configureren van e-mailstroom en routering in Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208328"
---
# <a name="mail-flow-in-eop"></a>E-mailstroom in EOP

In Microsoft 365-organisaties met Exchange Online-postvakken of zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken, gaan alle berichten die naar uw organisatie worden verzonden via EOP voordat uw werknemers ze zien. U hebt opties voor het routeren van berichten die via EOP worden verzonden voor verwerking voordat ze worden doorgestuurd naar de postvakken van uw werknemer.

## <a name="working-with-messages-and-message-access-options"></a>Werken met berichten en opties voor berichttoegang

EOP biedt flexibiliteit in de manier waarop uw berichten worden doorgestuurd. In de volgende onderwerpen worden stappen in het e-mailstroomproces uitgelegd.

[Directory based edge blocking gebruiken om berichten die naar ongeldige ontvangers worden verzonden, af te wijzen](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Directory Based Edge Blocking waarmee u berichten weigeren voor ongeldige ontvangers in de perimeter van het servicenetwerk.

[Beheerde domeinen weergeven of bewerken in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschrijft hoe u domeinen beheert die zijn gekoppeld aan uw EOP-service.

Als u subdomeinen aan uw organisatie toevoegt, kan uw EOP-service u ook helpen deze te beheren. Meer informatie over subdomeinen bij [E-mailstroom inschakelen voor subdomeinen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configureer e-mailstroom met behulp van connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceert connectors en laat zien hoe u ze gebruiken om e-mailroutering aan te passen. Scenario's omvatten het waarborgen van veilige communicatie met een partnerorganisatie en het opzetten van een slimme host.

[Met verbeterde filtering voor connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) wordt beschreven hoe u connectors configureert als uw e-mail vóór EOP naar een service of apparaat wordt doorgestuurd.

In zelfstandige EOP-organisaties moet u een paar configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt doorgestuurd naar de map met ongewenste e-mail van elke gebruiker. Deze worden beschreven in [Standalone EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Als u geen berichten naar de map met ongewenste e-mail van elke gebruiker wilt verplaatsen, u een andere actie kiezen door uw antispambeleid te bewerken (ook wel inhoudsfilterbeleid genoemd). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="verify-mail-flow"></a>E-mailstroom verifiëren

Zie de 'Hoe weet je dat deze taak heeft gewerkt', inclusief je connectorconfiguratie, om te controleren of je eop-setup, inclusief je connectorconfiguratie, goed werkt. sectie in [Uw EOP-service instellen](set-up-your-eop-service.md).

[Test de e-mailstroom door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) en geeft instructies voor het testen dat uw e-mailstroom correct is ingesteld.
