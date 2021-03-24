---
title: Stap 5. Apparaat- en app-beheer voor uw Microsoft 365 voor enterprise-tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implementeer de juiste optie voor apparaat- en app-beheer voor uw Microsoft 365-tenants.
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050992"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 5. Apparaat- en app-beheer voor uw Microsoft 365 voor enterprise-tenants

Microsoft 365 voor bedrijven bevat functies voor het beheren van apparaten en het gebruik van apps op die apparaten binnen uw organisatie met MDM (Mobile Device Management) en Mobile Application Management (MAM). U kunt iOS-, Android-, macOS- en Windows-apparaten beheren om de toegang tot de resources van uw organisatie, inclusief uw gegevens, te beschermen. U kunt bijvoorbeeld voorkomen dat e-mailberichten worden verzonden naar personen buiten uw organisatie of organisatiegegevens isoleren van persoonlijke gegevens op de persoonlijke apparaten van uw werknemer.

Hier ziet u een voorbeeld van de validatie en het beheer van gebruikers, hun apparaten en hun gebruik van lokale en cloudproductiviteits-apps zoals Microsoft Teams.

![Validatie en beheer van gebruikers, apparaten en apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Microsoft 365 voor bedrijven bevat functies voor het beheren van apparaten en de toegang tot apps om de resources van uw organisatie te beveiligen en te beveiligen. Er zijn twee opties voor apparaatbeheer:

- Microsoft Intune, een uitgebreide oplossing voor apparaat- en app-beheer voor ondernemingen.
- Basismobiliteit en beveiliging, een subset van Intune-services die is opgenomen in alle Microsoft 365-producten voor het beheren van apparaten in uw organisatie. Zie Mogelijkheden van [basismobiliteit](../admin/basic-mobility-security/capabilities.md)en beveiliging voor meer informatie.

Als u Microsoft 365 E3 of E5 hebt, moet u Intune gebruiken.

## <a name="microsoft-intune"></a>Microsoft Intune

U gebruikt [Microsoft Intune om](/mem/intune/fundamentals/planning-guide) de toegang tot uw organisatie te beheren met MDM of MAM. MDM is wanneer gebruikers hun apparaten 'registreren' in Intune. Nadat een apparaat is geregistreerd, is het een beheerd apparaat en kan het beleid, de regels en instellingen van uw organisatie worden ontvangen. U kunt bijvoorbeeld specifieke apps installeren, een wachtwoordbeleid maken, een VPN-verbinding installeren en meer.

Gebruikers met hun eigen persoonlijke apparaten willen hun apparaten mogelijk niet registreren of worden beheerd door Intune en het beleid van uw organisatie. Maar u moet nog steeds de resources en gegevens van uw organisatie beschermen. In dit scenario kunt u uw apps beveiligen met MAM. U kunt bijvoorbeeld een MAM-beleid gebruiken dat vereist dat een gebruiker een pincode in moet voeren bij toegang tot SharePoint op het apparaat.

U bepaalt ook hoe u persoonlijke apparaten en apparaten van de organisatie gaat beheren. Mogelijk wilt u apparaten anders behandelen, afhankelijk van hun gebruik.

## <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

Microsoft biedt een set configuraties voor identiteits- en [apparaattoegang](../security/defender-365-security/microsoft-365-policies-configurations.md) om een veilig en productief personeel te garanderen. Deze configuraties omvatten het gebruik van:

- Azure AD-beleid voor voorwaardelijke toegang
- Microsoft Intune-beleid voor apparaat compliance en app-beveiliging
- Beleid voor gebruikersrisico's voor Azure AD Identity Protection
- Aanvullende beleidsregels voor cloud-apps

Hier ziet u een voorbeeld van de toepassing van deze instellingen en beleidsregels om gebruikers, hun apparaten en hun gebruik van lokale en cloudproductiviteitsapps zoals Microsoft Teams te valideren en te beperken.

![Configuraties voor identiteits- en apparaattoegang voor vereisten en beperkingen voor gebruikers, hun apparaten en het gebruik van apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Gebruik de configuraties in deze artikelen voor apparaattoegang en app-beheer:

- [Vereisten](../security/defender-365-security/identity-access-prerequisites.md)
- [Algemeen beleid voor identiteiten en apparaattoegang](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultaten van stap 5

Voor apparaat- en app-beheer voor uw Microsoft 365-tenant hebt u de Intune-instellingen en -beleidsregels bepaald om gebruikers, hun apparaten en hun gebruik van lokale en cloudproductiviteitsapps te valideren en te beperken.

Hier is een voorbeeld van een tenant met Intune-apparaat- en app-beheer met de nieuwe elementen gemarkeerd.

![Voorbeeld van een tenant met Intune-apparaat- en app-beheer](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In deze afbeelding heeft de tenant:

- Apparaten die eigendom zijn van de organisatie die zijn geregistreerd bij Intune.
- Intune-apparaat- en app-beleid voor geregistreerde en persoonlijke apparaten.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Doorlopend onderhoud voor apparaat- en app-beheer

Op permanente basis moet u mogelijk het volgende doen: 

- Apparaatinschrijving beheren.
- Wijzig uw instellingen en beleid voor extra apps, apparaten en beveiligingsvereisten.