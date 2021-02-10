---
title: E-mailstroom in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Beheerder vindt meer informatie over de opties voor het configureren van de e-mailstroom en routering in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167237"
---
# <a name="mail-flow-in-eop"></a>E-mailstroom in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-organisaties met Exchange Online-postvakken of zelfstandige organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, worden alle berichten die naar uw organisatie worden verzonden, doorgestuurd via EOP voordat uw werknemers deze zien. U hebt opties voor het routeeren van berichten die via EOP worden verwerkt voordat deze worden doorvergeleid naar het Postvak IN van uw werknemer.

## <a name="working-with-messages-and-message-access-options"></a>Werken met opties voor berichten en berichttoegang

EOP biedt flexibiliteit in de manier waarop uw berichten worden omgeleid. In de volgende onderwerpen worden de stappen in het e-mailstroomproces uitgelegd.

[Randblokkering op basis van adreslijst gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Randblokkering op basis van adreslijst, waarmee u berichten kunt weigeren voor ongeldige geadresseerden aan de perimeter van het servicenetwerk.

[In Het weergeven of bewerken van beheerde](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) domeinen in EOP wordt beschreven hoe u domeinen kunt beheren die zijn gekoppeld aan uw EOP-service.

Als u subdomeinen aan uw organisatie toevoegt, kan uw EOP-service u helpen deze ook te beheren. Meer informatie over subdomeinen op [E-mailstroom inschakelen voor subdomeinen in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Configureer de e-mailstroom met connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) en laat zien hoe u deze kunt gebruiken om e-mailroutering aan te passen. Scenario's zijn onder andere het zorgen voor veilige communicatie met een partnerorganisatie en het instellen van een smart host.

[Met verbeterd filteren voor connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) wordt beschreven hoe u connectors configureert als uw e-mail wordt doorgestuurd naar een service of apparaat vóór EOP.

In zelfstandige EOP-organisaties moet u een aantal configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt doorverrouteerd naar de map ongewenste e-mail van elke gebruiker. Deze worden beschreven in zelfstandige EOP configureren om spam te leveren aan de map [Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Als u geen berichten wilt verplaatsen naar de map ongewenste e-mail van elke gebruiker, kunt u een andere actie kiezen door het antispambeleid (ook wel inhoudsfilterbeleid genoemd) te bewerken. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="verify-mail-flow"></a>E-mailstroom controleren

Als u wilt controleren of uw EOP-installatie, inclusief de configuratie van de connector, goed werkt, gaat u naar de pagina 'Hoe weet u of deze taak heeft gewerkt?' in de [sectie Uw EOP-service instellen.](set-up-your-eop-service.md)

[Test de e-mailstroom door uw Microsoft 365-connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) te valideren instructies voor het testen van uw e-mailstroom.
