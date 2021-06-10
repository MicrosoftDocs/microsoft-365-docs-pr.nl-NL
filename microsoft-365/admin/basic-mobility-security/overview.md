---
title: Overzicht van basismobiliteit en beveiliging voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Gebruik Basismobiliteit en beveiliging om beveiligingsbeleid en toegangsregels voor apparaten in te stellen.
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706308"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Overzicht van basismobiliteit en beveiliging voor Microsoft 365

U kunt mobiele apparaten beheren en beveiligen wanneer ze zijn verbonden met uw Microsoft 365 organisatie met basismobiliteit en beveiliging. Mobiele apparaten zoals smartphones en tablets die worden gebruikt om toegang te krijgen tot werk-e-mail, agenda, contactpersonen en documenten, spelen een grote rol om ervoor te zorgen dat werknemers hun werk altijd en overal kunnen doen. Het is dus essentieel dat u de gegevens van uw organisatie helpt beschermen wanneer mensen apparaten gebruiken. U kunt Basismobiliteit en beveiliging gebruiken om beveiligingsbeleid en toegangsregels voor apparaten in te stellen en mobiele apparaten te wissen als ze verloren of gestolen zijn.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Basisinstellingen voor mobiliteit en beveiliging":::

## <a name="what-types-of-devices-can-you-manage"></a>Welke typen apparaten kunt u beheren?

U kunt Basismobiliteit en beveiliging gebruiken om veel typen mobiele apparaten te beheren, zoals Windows Phone, Android, iPhone en iPad. Als u mobiele apparaten wilt beheren die door personen in uw organisatie worden gebruikt, moet elke persoon een toepasselijke Microsoft 365-licentie hebben en moet zijn of haar apparaat zijn geregistreerd in Basismobiliteit en Beveiliging.

Zie Mogelijkheden van basismobiliteit en beveiliging voor meer informatie over basismobiliteit en beveiliging voor elk type [apparaat.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Installatiestappen voor basismobiliteit en beveiliging

Een Microsoft 365 globale beheerder moet de volgende stappen volgen om Basismobiliteit en beveiliging te activeren en in te stellen. Volg de richtlijnen in Basismobiliteit en beveiliging instellen voor [gedetailleerde stappen.](set-up.md) 

Hier volgt een overzicht van de stappen:

**Stap 1:** Activeer Basismobiliteit en beveiliging door de stappen in  [basismobiliteit](set-up.md)en beveiliging instellen te volgen.

**Stap 2:** Stel Basismobiliteit en beveiliging in door bijvoorbeeld een APN-certificaat te maken voor het beheren van iOS-apparaten en het toevoegen van een DNS-record (Domain Name System) voor uw domein ter ondersteuning van Windows telefoons.

**Stap 3:** Maak apparaatbeleid en pas ze toe op groepen gebruikers. Wanneer u dit doet, ontvangen uw gebruikers een inschrijvingsbericht op hun apparaat en wanneer ze de inschrijving hebben voltooid, worden hun apparaten beperkt door het beleid dat u voor hen hebt ingesteld. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Beleidsinstellingen voor basisbeveiliging en mobiliteit":::

## <a name="device-management-tasks"></a>Apparaatbeheertaken

Nadat u Basismobiliteit en Beveiliging hebt ingesteld en uw gebruikers hun apparaten hebben geregistreerd, kunt u de apparaten beheren, de toegang blokkeren of een apparaat wissen, indien nodig. Zie Apparaten beheren die zijn geregistreerd voor Mobile Device [Management](manage-enrolled-devices.md)voor Microsoft 365.

## <a name="other-ways-to-manage-devices-and-apps"></a>Andere manieren om apparaten en apps te beheren

Als u alleen mobile app management (MAM) nodig hebt, misschien voor personen die werkprojecten bijwerken op hun eigen apparaten, biedt Intune een andere optie dan het registreren en beheren van apparaten. Met een Intune-abonnement kunt u MAM-beleid instellen via de Azure-portal, zelfs als de apparaten van personen niet zijn geregistreerd in Intune. Zie Overzicht van [app-beveiligingsbeleid voor meer informatie.](/mem/intune/apps/app-protection-policy)

## <a name="related-content"></a>Verwante onderwerpen

[Basismobiliteit en beveiliging instellen](set-up.md) (artikel)\
[Uw mobiele apparaat registreren met basismobiliteit en beveiliging](enroll-your-mobile-device.md) (artikel)\
[Apparaten beheren die zijn geregistreerd voor Mobile Device Management voor Microsoft 365](manage-enrolled-devices.md) (artikel)\
[Meer informatie over apparaten die worden beheerd door Basismobiliteit en Beveiliging](get-details-about-managed-devices.md) (artikel)