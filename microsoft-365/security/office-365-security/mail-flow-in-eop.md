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
description: Beheerder kan meer informatie krijgen over de opties voor het configureren van e-mailstroom en routering in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ad80c4176c1b8b1c47b6b9ecafd34b4ca301f3f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623415"
---
# <a name="mail-flow-in-eop"></a>E-mailstroom in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met Exchange Online-postvakken of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, worden alle berichten die naar uw organisatie worden verzonden, via EOP verzonden voordat uw werknemers deze zien. U hebt opties voor het doorverzenden van berichten die via EOP worden verzonden voor verwerking voordat ze worden doorgeleid naar uw postvak IN van uw werknemer.

## <a name="working-with-messages-and-message-access-options"></a>Werken met opties voor berichten en berichttoegang

EOP biedt flexibiliteit in de manier waarop uw berichten worden gerouteerd. In de volgende onderwerpen worden de stappen in het e-mailstroomproces uitgelegd.

[Randblokkering op basis van adreslijst gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Randblokkering op basis van adreslijst waarmee u berichten voor ongeldige geadresseerden kunt weigeren in de perimeter van het servicenetwerk.

[In Beheerde domeinen weergeven](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) of bewerken in EOP wordt beschreven hoe u domeinen beheert die zijn gekoppeld aan uw EOP-service.

Als u subdomeinen toevoegt aan uw organisatie, kan uw EOP-service u helpen deze ook te beheren. Meer informatie over subdomeinen bij [E-mailstroom inschakelen voor subdomeinen in](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)Exchange Online.

[Als u de e-mailstroom configureert met](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) behulp van verbindingslijnen, worden verbindingslijnen gebruikt en ziet u hoe u deze kunt gebruiken om e-mailroutering aan te passen. Scenario's zijn onder andere zorgen voor veilige communicatie met een partnerorganisatie en het instellen van een slimme host.

[Verbeterde filtering voor verbindingslijnen](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschrijft hoe u verbindingslijnen configureert als uw e-mail wordt doorgestuurd naar een service of apparaat vóór EOP.

In hybride omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de uitspraak voor EOP-spamfilters te vertalen, zodat de regel voor ongewenste e-mail het bericht naar de map Ongewenste e-mail kan verplaatsen. Zie [EOP configureren voor spam](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)in de map Ongewenste e-mail in hybride omgevingen voor meer informatie. Als u berichten niet naar de map Ongewenste e-mail van elke gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw antispambeleid te bewerken (ook wel bekend als beleid voor inhoudsfilters). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="verify-mail-flow"></a>E-mailstroom controleren

Zie 'Hoe weet u dat deze taak heeft gewerkt?' als u wilt controleren of uw EOP-instelling, inclusief de configuratie van de connector, correct werkt. sectie in [Uw EOP-service instellen.](/exchange/standalone-eop/set-up-your-eop-service)

[Test de e-mailstroom door uw Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) te valideren, zodat u kunt testen of de e-mailstroom correct is ingesteld.
