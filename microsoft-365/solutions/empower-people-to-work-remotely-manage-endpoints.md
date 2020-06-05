---
title: Stap 3. Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Gebruik Microsoft Endpoint Manager om uw apparaten, pc's en andere eindpunten te beheren.
ms.openlocfilehash: c7149295c24e5339e87db55998ec48fe9f0e9a93
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560491"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Stap 3. Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren

Als u externe medewerkers hebt, moet u steeds meer persoonlijke apparaten ondersteunen. Eindpuntbeheer biedt op beleid gebaseerde beveiliging waarbij apparaten moeten voldoen aan specifieke criteria voordat ze toegang krijgen tot bronnen. Microsoft Endpoint Manager biedt moderne beheermogelijkheden om uw gegevens in de cloud en on-premises veilig te houden. 

Endpoint Manager biedt services en hulpprogramma‘s voor het beheer van mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers door enkele services te combineren die u mogelijk al kent en gebruikt:

![De onderdelen voor eindpuntbeheer](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Intune is ontworpen om u te helpen gegevens te beschermen wanneer de gegevens van uw organisatie toegankelijk zijn vanaf apparaten die niet door u worden beheerd. Met het beleid voor app-bescherming van Intune in combinatie met voorwaardelijke toegang in Azure Active Directory (Azure AD) hebt u gedetailleerde controle over de gegevens op mobiele apparaten. Met Intune kunt u ook uitgebreid beleid definiëren waardoor alleen de juiste mensen onder de juiste omstandigheden toegang hebben tot uw bedrijfsgegevens. U kunt ervoor zorgen dat de gegevens beschermd blijven door te bepalen hoe deze worden gebruikt in Office, Outlook en andere mobiele apps.

Zie voor meer informatie dit [overzicht van Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager is een on-premises beheeroplossing voor het beheer van desktops, servers en laptops op uw netwerk of op internet. U kunt de oplossing in de cloud gebruiken voor integratie met Intune, Azure AD, Microsoft Defender ATP en andere cloudservices. Gebruik Configuration Manager om apps, software-updates en besturingssystemen te implementeren. U kunt ook toezicht houden op naleving, clients in real time doorzoeken en hiermee communiceren, en nog veel meer.

Zie voor meer informatie dit [overzicht van Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-management

Met co-management wordt uw bestaande on-premises Configuration Manager gekoppeld aan de cloud via Intune en andere Microsoft 365-cloudservices. U kiest of u Configuration Manager of Intune wilt gebruiken als beheerautoriteit voor de zeven verschillende werklastgroepen.

Co-management is een onderdeel van Endpoint Manager dat gebruikmaakt van cloudfuncties, waaronder voorwaardelijke toegang. U kunt bepaalde taken on-premises blijven doen terwijl u andere taken in de cloud uitvoert met Intune.

Zie voor meer informatie dit [overzicht van co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics is een cloudservice die kan worden geïntegreerd met Configuration Manager en die u inzicht en informatie biedt, zodat u weloverwogen beslissingen kunt nemen over uw Windows-clients. De service combineert gegevens van uw organisatie met gegevens verzameld van miljoenen apparaten die zijn verbonden met Microsoft-cloudservices. Met Desktop Analytics kunt u een inventarisatie maken van apps die in uw organisatie worden uitgevoerd, de compatibiliteit van apps beoordelen met de nieuwste functie-updates voor Windows 10, compatibiliteitsproblemen identificeren en suggesties voor risicobeperking ontvangen op basis van gegevensinzichten in de cloud, pilotgroepen maken die model staan voor alle toepassingen en stuurprogramma's op een minimale set apparaten, en Windows 10 implementeren op apparaten die worden beheerd voor testen en productie.

Zie voor meer informatie dit [overzicht van Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot is een zero-touch, selfservice Windows-implementatieplatform. Het platform bevat een verzameling technologieën die worden gebruikt om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik. U kunt Windows Autopilot ook gebruiken om apparaten opnieuw in te stellen, aan te passen en te herstellen. De IT-afdeling kan dit doen via een gemakkelijk en eenvoudig proces en (bijna) zonder infrastructuur om te beheren. De apparaten voor gebruikers kunnen met slechts enkele eenvoudige bewerkingen worden klaargemaakt voor gebruik. En IT-professionals hoeven er alleen maar voor te zorgen dat eindgebruikers verbinding kunnen maken met een netwerk door hun referenties te verifiëren.

Voor meer informatie raadpleegt u dit [overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Technische bronnen voor eindpuntbeheerders

- [De video Deel 3 over het beheren van Windows 10-apparaten voor externe werknemers](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [De video Deel 5 over het beheren van gebruikersdesktops en browsers voor externe werknemers](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [Een mobiliteitsinfrastructuur voor Microsoft 365 implementeren](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Verschillende typen apparaten inschrijven voor het beheer van mobiele apparaten](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Uw eindgebruikers informeren over Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Resultaten van stap 3

U gebruikt de reeks functies en mogelijkheden van Endpoint Manager om mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers te beheren.

## <a name="next-step"></a>Volgende stap

Ga verder met [stap 4](empower-people-to-work-remotely-teams-productivity-apps.md) om externe toegang te bieden tot on-premises apps en services.
