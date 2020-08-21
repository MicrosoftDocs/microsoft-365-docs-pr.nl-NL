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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Beheerder biedt informatie over de opties voor het configureren van e-mail stroom en routering in Exchange Online Protection (EOP).
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827723"
---
# <a name="mail-flow-in-eop"></a>E-mailstroom in EOP

In Microsoft 365-organisaties met postvakken van Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken worden alle berichten die naar uw organisatie worden verzonden, doorgestuurd naar EOP voordat ze de werknemers zien. U hebt opties voor het doorsturen van berichten die door EOP worden verwerkt voordat ze worden doorgestuurd naar de postvakken van uw werknemers.

## <a name="working-with-messages-and-message-access-options"></a>Werken met berichten en opties voor het openen van berichten

EOP biedt flexibiliteit bij het routeren van uw berichten. In de volgende onderwerpen wordt stapsgewijs uitgelegd hoe u de e-mail stroom procedure uitvoert.

[Op mappen gebaseerde rand blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) wijzen Een beschrijving van de functie voor het blokkeren van basis op basis van een rand die u kunt gebruiken om berichten voor ongeldige geadresseerden op de netwerk blokkering te weigeren

[Beheerde domeinen weergeven of bewerken in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) wordt beschreven hoe u domeinen kunt beheren die aan uw EOP-service zijn gekoppeld.

Als u subdomeinen toevoegt aan uw organisatie, kunt u deze ook door de EOP-service beheren. Meer informatie over subdomeinen vindt u [in e-mail stroom inschakelen voor subdomeinen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[E-mail stroom configureren met connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceert verbindingslijnen en laat zien hoe u deze kunt gebruiken om e-mail routering aan te passen. Scenario's zijn voor veilig communiceren met een partnerorganisatie en het instellen van een Smart host.

[Uitgebreid filteren op connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) hierin wordt beschreven hoe u connectors kunt configureren als uw e-mail wordt gerouteerd naar een service of apparaat vóór EOP.

In zelfstandige EOP-organisaties moet u een paar configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt gerouteerd naar de map Ongewenste e-mail in elke gebruiker. Deze informatie wordt uitvoerig beschreven in [zelfstandige EOP configureren voor spam op de map Ongewenste e-mail in hybride omgevingen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Als u berichten niet naar de map Ongewenste e-mail wilt verplaatsen naar de map Ongewenste e-mail, kunt u een andere actie kiezen door uw Antispambeleid te bewerken (ook wel inhouds filter beleid genoemd). Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="verify-mail-flow"></a>De e-mail stroom controleren

Als u wilt controleren of de EOP-instellingen, waaronder de connectorconfiguratie, goed werken, raadpleegt u de sectie Hoe weet u dat deze taak heeft gewerkt? sectie voor [het instellen van uw EOP-service](set-up-your-eop-service.md).

[De e-mail stroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) bevat instructies voor het testen van de juiste configuratie van uw e-mail stroom.
