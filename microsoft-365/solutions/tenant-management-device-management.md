---
title: Stap 5. Apparaten en apps beheren voor uw Microsoft 365 for Enterprise-tenants
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
ms.custom:
- Ent_Solutions
description: Implementeer de juiste optie voor apparatuur en app-beheer voor uw Microsoft 365-tenants.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908507"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 5. Apparaten en apps beheren voor uw Microsoft 365 for Enterprise-tenants

Microsoft 365 voor Enterprise bevat functies waarmee u apparaten en het gebruik van apps op deze apparaten binnen uw organisatie kunt beheren met een MDM (Mobile Device Management) en Mobile Application Management (MAM). U kunt apparaten van iOS, Android, macOS en Windows beheren om de toegang tot de bronnen van uw organisatie te beschermen, waaronder uw gegevens. U kunt voorkomen dat e-mailberichten naar personen buiten uw organisatie worden verzonden of organisatiegegevens van persoonlijke gegevens op de persoonlijke apparaten van de werknemer isoleren.

Hier ziet u een voorbeeld van de validering en het beheer van gebruikers, de bijbehorende apparaten en het gebruik van apps voor lokale en Cloud productiviteit, zoals Microsoft teams.

![Validatie en beheer van gebruikers, apparaten en apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Microsoft 365 for Enterprise bevat functies waarmee u apparaten en hun toegang tot apps kunt beschermen en beschermen. Er zijn twee opties voor Apparaatbeheer:

- Microsoft intune (dit is een uitgebreide oplossing voor apparatuur en app-beheer) voor ondernemingen.
- Basis mobiliteit en beveiliging, een subset van intune-services die deel uitmaken van alle Microsoft 365-producten voor het beheren van apparaten in uw organisatie. Zie [mogelijkheden van basis mobiliteit en beveiliging](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)voor meer informatie.

Als u Microsoft 365 E3 of E5 hebt, gebruikt u intune.

## <a name="microsoft-intune"></a>Microsoft Intune

U kunt [Microsoft intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) gebruiken om de toegang tot uw organisatie te beheren via MDM of mam. MDM is wanneer gebruikers de optie hun apparaat registreren in intune. Als een apparaat is ingeschreven, is dit een beheerd apparaat en kan het beleid, de regels en instellingen van uw organisatie worden ontvangen. U kunt bijvoorbeeld bepaalde apps installeren, een wachtwoordbeleid maken, een VPN-verbinding installeren en nog veel meer.

Gebruikers met hun eigen persoonlijke apparaten willen hun apparaten mogelijk niet registreren of worden beheerd door intune en het beleid van uw organisatie. U moet de bronnen en gegevens van uw organisatie nog altijd beschermen. In dit scenario kunt u uw apps beschermen met behulp van MAM. U kunt bijvoorbeeld een MAM-beleid gebruiken waarbij een gebruiker een pincode moet invoeren bij het openen van SharePoint op het apparaat.

U kunt ook bepalen hoe u persoonlijke apparaten en apparaten met de eigen organisatie gaat beheren. U kunt apparaten anders behandelen, afhankelijk van hun gebruik.

## <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

Microsoft biedt een reeks configuraties voor [identiteit en Apparaattoegang,](../security/office-365-security/microsoft-365-policies-configurations.md) zodat u zich kunt beschermen tegen een veilig en productief personeel. Voor deze configuraties gelden de volgende opties:

- Azure AD-beleid voor voorwaardelijke toegang
- Naleving van Microsoft intune-apparaat en beleid voor app-beveiliging
- Azure AD Identity Protection User Risk policies
- Extra beleidsregels voor Cloud-apps

Hier ziet u een voorbeeld van de toepassing van deze instellingen en beleidsregels voor het valideren en beperken van gebruikers, hun apparaten, en het gebruik van de apps voor lokale en Cloud productiviteit zoals Microsoft teams.

![Configuraties voor identiteits-en Apparaattoegang voor vereisten en beperkingen voor gebruikers, hun apparaten en het gebruik van apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Gebruik voor toegang tot apparaten en app-beheer de configuraties in de volgende artikelen:

- [Vereisten](../security/office-365-security/identity-access-prerequisites.md)
- [Algemeen beleid voor identiteiten en apparaattoegang](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultaten van stap 5

Voor apparaat-en app-beheer voor uw Microsoft 365-Tenant hebt u de intune-instellingen en het beleid vastgesteld voor het valideren en beperken van gebruikers, hun apparaten en het gebruik van de apps voor lokale en Cloud productiviteit.

Hier ziet u een voorbeeld van een Tenant met intune-apparaat en app-beheer waarbij de nieuwe elementen zijn gemarkeerd.

![Voorbeeld van een Tenant met intune-apparaat en app-beheer](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In deze afbeelding is de Tenant:

- Apparaten met een organisatie die zijn geregistreerd voor intune.
- InTune-apparaat en app-beleid voor ingeschreven en persoonlijke apparaten.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Voortdurend onderhoud van apparatuur en apps beheren

Het kan zijn dat u het volgende moet doen: 

- De registratie van apparaten beheren.
- De instellingen en het beleid voor extra apps, apparaten en beveiligingsvereisten wijzigen.
