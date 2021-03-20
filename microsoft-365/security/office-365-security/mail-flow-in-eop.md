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
description: Beheerder vindt meer informatie over de opties voor het configureren van e-mailstroom en routering in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907024"
---
# <a name="mail-flow-in-eop"></a>E-mailstroom in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met Exchange Online-postvakken of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, worden alle berichten die naar uw organisatie worden verzonden, via EOP verzonden voordat uw werknemers deze zien. U hebt opties voor het doorverzenden van berichten die via EOP worden verzonden voor verwerking voordat ze worden doorgeleid naar uw postvak IN van uw werknemer.

## <a name="working-with-messages-and-message-access-options"></a>Werken met opties voor berichten en berichttoegang

EOP biedt flexibiliteit in de manier waarop uw berichten worden gerouteerd. In de volgende onderwerpen worden de stappen in het e-mailstroomproces uitgelegd.

[Randblokkering op basis van adreslijst gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Randblokkering op basis van adreslijst waarmee u berichten voor ongeldige geadresseerden kunt weigeren in de perimeter van het servicenetwerk.

[In Beheerde domeinen weergeven](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) of bewerken in EOP wordt beschreven hoe u domeinen beheert die zijn gekoppeld aan uw EOP-service.

Als u subdomeinen toevoegt aan uw organisatie, kan uw EOP-service u helpen deze ook te beheren. Meer informatie over subdomeinen bij [E-mailstroom inschakelen voor subdomeinen in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Als u de e-mailstroom configureert met](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) behulp van verbindingslijnen, worden verbindingslijnen gebruikt en ziet u hoe u deze kunt gebruiken om e-mailroutering aan te passen. Scenario's zijn onder andere zorgen voor veilige communicatie met een partnerorganisatie en het instellen van een slimme host.

[Verbeterde filtering voor verbindingslijnen](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschrijft hoe u verbindingslijnen configureert als uw e-mail wordt doorgestuurd naar een service of apparaat vóór EOP.

In zelfstandige EOP-organisaties moet u een paar configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt doorgeleid naar de map ongewenste e-mail van elke gebruiker. Deze worden beschreven in Zelfstandige EOP configureren om spam te verzenden naar de map [Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Als u berichten niet naar de map ongewenste e-mail van elke gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw antispambeleid (ook wel inhoudsfilterbeleid genoemd) te bewerken. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="verify-mail-flow"></a>E-mailstroom controleren

Zie 'Hoe weet u dat deze taak heeft gewerkt?' als u wilt controleren of uw EOP-instelling, inclusief de configuratie van de connector, correct werkt. sectie in [Uw EOP-service instellen.](set-up-your-eop-service.md)

[Test de e-mailstroom door uw Microsoft 365-connectors](/exchange/mail-flow-best-practices/test-mail-flow) te valideren, zodat u kunt testen of uw e-mailstroom correct is ingesteld.