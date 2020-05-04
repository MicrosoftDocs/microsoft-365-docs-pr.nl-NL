---
title: 3. Implementeer endpoint management voor uw apparaten, pc's en andere eindpunten
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Gebruik Microsoft Endpoint Manager om uw apparaten, pc's en andere eindpunten te beheren.
ms.openlocfilehash: fdfe38a25947312b878b03734c320de004762506
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002707"
---
# <a name="3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>3. Implementeer endpoint management voor uw apparaten, pc's en andere eindpunten

Met externe medewerkers moet u een groeiend aantal persoonlijke apparaten ondersteunen. Endpoint management is een op beleid gebaseerde benadering van beveiliging waarbij apparaten moeten voldoen aan specifieke criteria voordat ze toegang krijgen tot bronnen. Microsoft Endpoint Manager biedt een moderne werkplek en moderne beheermogelijkheden om uw gegevens in de cloud en op locatie veilig te houden. 

Endpoint Manager biedt services en hulpprogramma‘s voor het beheer van mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers door de volgende services te combineren die u mogelijk al kent en gebruikt.

## <a name="microsoft-intune"></a>Microsoft Intune

Intune is ontworpen om u te helpen gegevens te beschermen wanneer u de apparaten die worden gebruikt om toegang te krijgen tot organisatiegegevens niet beheert. Beleid voor app-bescherming van Intune in combinatie met voorwaardelijke toegang in Azure AD biedt gedetailleerde controle over gegevens op mobiele apparaten. Met Intune kunt u ook uitgebreid beleid definiëren waarmee alleen de juiste mensen onder de juiste omstandigheden toegang hebben tot uw bedrijfsgegevens. U kunt ervoor kunnen zorgen dat de gegevens beschermd blijven door te bepalen hoe ze deze gebruiken in Office, Outlook en andere mobiele apps.

Zie dit [overzicht van Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune)voor meer informatie.

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager is een on-premises beheeroplossing voor het beheren van desktops, servers en laptops op uw netwerk of op internet. U kunt het in de cloud inschakelen voor integratie met Intune, Azure AD, Microsoft Defender ATP en andere cloudservices. Gebruik Configuration Manager om apps, software-updates en besturingssystemen te implementeren. U kunt ook in realtime toezicht houden op naleving, vragen stellen aan en reageren op klanten, en nog veel meer.

Zie dit [overzicht van Configuration Manager](https://docs.microsoft.com/configmgr/core/understand/introduction)voor meer informatie.

## <a name="co-management"></a>Co-management

Co-management combineert uw bestaande on-premises Configuration Manager met de cloud met behulp van Intune en andere Microsoft 365-cloudservices. U kiest of Configuration Manager of Intune de beheerautoriteit is voor de zeven verschillende werklastgroepen.

Als onderdeel van Endpoint Manager gebruikt co-management cloudfuncties, waaronder voorwaardelijke toegang. U kunt bepaalde taken on-premises behouden terwijl u andere taken in de cloud uitvoert met Intune.

Zie voor meer informatie dit [overzicht van co-management](https://docs.microsoft.com/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Bureaubladanalyse

Bureaubladanalyse is een cloudgebaseerde service die kan worden geïntegreerd met Configuration Manager en die u inzicht en informatie biedt, zodat u weloverwogen beslissingen kunt nemen over uw Windows-clients. Het combineert gegevens van uw organisatie met gegevens die zijn verzameld van miljoenen apparaten die zijn verbonden met Microsoft-cloudservices. Met Bureaubladanalyse kunt u een inventarisatie maken van apps die in uw organisatie worden uitgevoerd, app-compatibiliteit beoordelen met de nieuwste functie-updates voor Windows 10, compatibiliteitsproblemen identificeren en mitigatiesuggesties ontvangen op basis van gegevensinzichten in de cloud, pilotgroepen maken die de gehele applicatie- en driverstatus representeren op een minimale set apparaten en Windows 10 voor pilot- en productie-beheerde apparaten implementeren.

Zie voor meer informatie dit [overzicht van bureaubladanalyse](https://docs.microsoft.com/configmgr/desktop-analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot is een zero-touch, self-service Windows-implementatieplatform. Het bevat een verzameling technologieën die worden gebruikt om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik. U kunt Windows Autopilot ook gebruiken om apparaten opnieuw in te stellen, opnieuw te gebruiken en te herstellen. Met deze oplossing kan een IT-afdeling het bovenstaande met weinig te beheren infrastructuur bereiken, met een proces dat gemakkelijk en eenvoudig is. Vanuit het oogpunt van de gebruiker zijn er slechts enkele eenvoudige bewerkingen nodig om hun apparaat klaar te maken voor gebruik. Vanuit het perspectief van de IT-professional is de enige interactie die de eindgebruiker moet uitvoeren om verbinding te maken met een netwerk en om hun referenties te verifiëren.

Voor meer informatie raadpleegt u dit [overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Technische bronnen voor beheerders voor endpoint management

- [Registreer beheerde apparaten voor beveiliging, maak gebruik van app-instellingen voor onbeheerde apparaten en gebruik apparaat- en app-beleid](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Verschillende typen apparaten inschrijven voor Mobile Device Management (MDM)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Hoe u uw eindgebruikers kunt informeren over Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Resultaten van stap 3

U gebruikt de reeks functies en mogelijkheden van Endpoint Manager om mobiele apparaten, desktopcomputers, virtuele machines, ingesloten apparaten en servers te beheren.

## <a name="next-step"></a>Volgende stap

Ga verder met [stap 4](empower-people-to-work-remotely-teams-productivity-apps.md) om externe toegang te bieden tot on-premises-apps en -services.
