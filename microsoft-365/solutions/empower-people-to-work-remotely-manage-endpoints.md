---
title: Stap 4. Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Gebruik Microsoft Endpoint Manager om uw apparaten, pc's en andere eindpunten te beheren.
ms.openlocfilehash: db06c7d65da1939ffbb04db64ea901e211b074f6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918336"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Stap 4. Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren

Als u externe medewerkers hebt, moet u steeds meer persoonlijke apparaten ondersteunen. Eindpuntbeheer biedt op beleid gebaseerde beveiliging waarbij apparaten moeten voldoen aan specifieke criteria voordat ze toegang krijgen tot bronnen. Microsoft Endpoint Manager biedt moderne beheermogelijkheden om uw gegevens in de cloud en on-premises veilig te houden. 

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) biedt services en hulpprogramma‘s voor het beheer van mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers door enkele services te combineren die u mogelijk al kent en gebruikt.

![De onderdelen van endpoint Management voor Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune is een cloudservice die gericht is op Mobile Device Management (MDM) en Mobile Application Management (MAM) dat deel uitmaakt van Microsoft 365. 

- **MDM:** geeft u volledige controle over apparaten die eigendom zijn van de organisatie, inclusief het bewerken van instellingen, functies en beveiliging. Apparaten zijn 'geregistreerd' in Intune waar ze Intune-beleid met regels en instellingen ontvangen. U kunt bijvoorbeeld wachtwoord- en PIN-vereisten instellen, een VPN-verbinding aanmaken, bedreigingsbeveiliging instellen en meer.

- **MAM:** externe werknemers willen misschien niet dat u volledige controle hebt over hun persoonlijke apparaten, ook wel bekend als Bring-Your-Own-Device (BYOD). U kunt voor externe werknemers opties beschikbaar maken en toch uw organisatie beschermen. Zo kunnen externe werknemers hun apparaten registreren voor volledige toegang tot de resources van uw organisatie. Als deze gebruikers alleen toegang willen tot e-mail of Microsoft Teams, kunt u app-beveiligingsbeleid gebruiken waarvoor meervoudige verificatie (MFA) vereist is om deze apps te kunnen gebruiken.

Zie voor meer informatie dit [overzicht van Microsoft Intune](/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager is een on-premises beheeroplossing voor het beheer van desktops, servers en laptops op uw netwerk of op internet. Gebruik Configuration Manager om apps, software-updates en besturingssystemen te implementeren. U kunt ook toezicht houden op naleving, clients in real time doorzoeken en hiermee communiceren, en nog veel meer. U kunt cloudtoegang inschakelen voor integratie met Intune, Azure AD, Microsoft Defender voor Eindpunt en andere cloudservices. 

Zie voor meer informatie dit [overzicht van Configuration Manager](/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-management

Met co-management wordt uw bestaande on-premises Configuration Manager gekoppeld aan de cloud via Intune en andere Microsoft 365-cloudservices. Kies of u Configuration Manager of Intune wilt gebruiken als instantie voor het beheer van wisselende werkbelasting. 

Bij het gebruik van co-management worden cloudfuncties op basis van Intune gebruikt, waaronder voorwaardelijke toegang en het afdwingen van apparaatcompliance. U kunt bepaalde taken on-premises blijven doen terwijl u andere taken in de cloud uitvoert.

Zie voor meer informatie dit [overzicht van co-management](/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics is een cloudservice die kan worden geïntegreerd met Configuration Manager en die u inzicht en informatie biedt, zodat u weloverwogen beslissingen kunt nemen over uw Windows-clients. De service combineert gegevens van uw organisatie met gegevens verzameld van miljoenen andere apparaten die zijn verbonden met Microsoft-cloudservices. 

Met Desktop Analytics kunt u het volgende doen:

- Een inventaris maken van apps die in uw organisatie worden gebruikt.
- Compatibiliteit van de app met de meest recente functie-updates voor Windows 10 verifiëren.
- Compatibiliteitsproblemen opsporen en suggesties voor risicobeperking ontvangen die zijn gebaseerd op gegevensinzichten uit de cloud.
- Testfasegroepen aanmaken die de gehele toepassing en stuurprogramma‘s op een minimale verzameling apparaten vertegenwoordigen.
- Implementeer Windows 10 op testfase- en productieapparaten.

Zie voor meer informatie dit [overzicht van Desktop Analytics](/mem/configmgr/desktop-analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot is een zero-touch, selfservice Windows-implementatieplatform. Het platform bevat een verzameling technologieën die worden gebruikt om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik. U kunt Windows Autopilot ook gebruiken om apparaten opnieuw in te stellen, aan te passen en te herstellen. 

Met Windows Autopilot kan een IT-afdeling apparaten vooraf configureren via een eenvoudig proces, nagenoeg zonder het beheer van enige infrastructuur. 

- De apparaten voor gebruikers kunnen met slechts enkele eenvoudige bewerkingen worden klaargemaakt voor gebruik. 
- En IT-professionals hoeven er alleen maar voor te zorgen dat eindgebruikers verbinding kunnen maken met een netwerk door hun referenties te verifiëren.

Voor meer informatie raadpleegt u dit [overzicht van Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Technische bronnen voor eindpuntbeheerders

- [Routekaart voor Apparaatbeheer voor Microsoft 365](../enterprise/device-management-roadmap-microsoft-365.md)
- [Verschillende typen apparaten inschrijven voor het beheer van mobiele apparaten](/mem/intune/enrollment/device-enrollment)
- [Uw eindgebruikers informeren over Microsoft Intune](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>Resultaten van stap 4

U gebruikt de reeks functies en mogelijkheden van Endpoint Manager om mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers te beheren.

## <a name="next-step"></a>Volgende stap

[![Stap 5: Productiviteitsapps en -services voor externe medewerkers implementeren](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)

Ga verder met [stap 5](empower-people-to-work-remotely-teams-productivity-apps.md) om te zorgen dat externe werknemers productiviteits-apps voor Microsoft 365 gaan gebruiken, zoals Microsoft Teams.