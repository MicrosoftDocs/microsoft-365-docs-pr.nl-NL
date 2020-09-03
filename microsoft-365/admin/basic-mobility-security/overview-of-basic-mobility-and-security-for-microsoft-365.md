---
title: Overzicht van basis mobiliteit en beveiliging voor Microsoft 365
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
description: Basis mobiliteit en beveiliging gebruiken voor het instellen van beveiligingsbeleid en toegangsregels voor apparaten.
ms.openlocfilehash: 7c1a4bc5ddf476463788f99305215ee6853190f1
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336816"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Overzicht van basis mobiliteit en beveiliging voor Microsoft 365

Met basis mobiliteit en beveiliging kunt u mobiele apparaten beheren en beveiligen wanneer ze verbinding maken met uw Microsoft 365-organisatie. Mobiele apparaten zoals smartphones en tablets die worden gebruikt om toegang te krijgen tot e-mail, agenda, contactpersonen en documenten, spelen een groot deel om ervoor te zorgen dat werknemers op elk gewenst moment, overal en op elk gewenst moment werk doen. Daarom is het essentieel dat u de gegevens van uw organisatie helpt beschermen wanneer gebruikers apparaten gebruiken. U kunt basis mobiliteit en beveiliging gebruiken om beveiligingsbeleid en toegangsregels voor apparaten in te stellen en mobiele apparaten te wissen wanneer ze verloren of gestolen zijn.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Basisinstellingen voor mobiliteit en beveiliging":::

## <a name="what-types-of-devices-can-you-manage"></a>Welke soorten apparaten kunt u beheren?

U kunt basis mobiliteit en beveiliging gebruiken voor het beheren van veel typen mobiele apparaten, zoals Windows Phone, Android, iPhone en iPad. Als u mobiele apparaten wilt beheren die door personen in uw organisatie worden gebruikt, moet elke persoon een toepasselijke Microsoft 365-licentie en hun apparaat registreren voor eenvoudige mobiliteit en beveiliging.

Zie [mogelijkheden van basis mobiliteit en beveiliging](capabilities-of-basic-mobility-and-secruity.md)om te zien welke basis mobiliteit en beveiliging voor elk type apparaat worden ondersteund.

## <a name="setup-steps-for-basic-mobility-and-security"></a>Instellingsstappen voor eenvoudige mobiliteit en beveiliging

Een globale beheerder van Microsoft 365 moet de volgende stappen uitvoeren om basis mobiliteit en beveiliging in te schakelen en in te stellen. Voor uitgebreide stappen volgt u de richtlijnen in [eenvoudige mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md). 

Hieronder ziet u een overzicht van de stappen:

**Stap 1:** Activeer basis mobiliteit en beveiliging door de volgende stappen uit te voeren in de tabel [basis mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md).

**Stap 2:** Stel basis mobiliteit en beveiliging in, bijvoorbeeld bij het maken van een APNs-certificaat voor het beheren van iOS-apparaten en het toevoegen van een DNS-record (Domain Name System) voor uw domein ter ondersteuning van Windows phones.

**Stap 3:** Beleidsregels voor apparaten maken en deze op groepen gebruikers toepassen. Wanneer u dit doet, worden de apparaten door uw gebruikers weergegeven op het apparaat en na het voltooien van de registratie, dan zijn de apparaten beperkt met de beleidsregels die u hebt ingesteld. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device-using-basic-mobility-and-security.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basisinstellingen voor beveiliging en mobiliteits beleid":::

## <a name="device-management-tasks"></a>Beheertaken voor apparaten

Nadat u eenvoudige mobiliteit en beveiliging hebt ingesteld en uw gebruikers hun apparaten hebben ingeschreven, kunt u de apparaten beheren, Access blokkeren of een apparaat wissen, indien nodig. Als u meer wilt weten over veelvoorkomende beheertaken, waaronder de functies voor het voltooien van de taken, raadpleegt u [apparaten beheren die zijn geregistreerd voor Mobile Device Management voor Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Andere manieren om apparaten en apps te beheren

Als u alleen een Mobile App Management (MAM) nodig hebt, kunnen gebruikers werk projecten bijwerken op hun eigen apparaten, en intune biedt een andere optie naast het registreren en beheren van apparaten. Met een intune-abonnement kunt u MAM-beleidsregels instellen met behulp van de Azure-Portal, zelfs als de apparaten van de personen niet zijn ingeschreven voor intune. Voor meer informatie raadpleegt u [overzicht van app-beveiligingsbeleid](https://go.microsoft.com/fwlink/?LinkId=2132517).

## <a name="related-topics"></a>Verwante onderwerpen

[Eenvoudige mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md)

[Uw mobiele apparaat registreren met basis mobiliteit en beveiliging](enroll-your-mobile-device-using-basic-mobility-and-security.md)

[Apparaten beheren die zijn geregistreerd voor Mobile Device Management voor Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md)

[Meer informatie over apparaten die worden beheerd door basis mobiliteit en beveiliging](get-details-about-basic-mobility-and-security-managed-devices.md)