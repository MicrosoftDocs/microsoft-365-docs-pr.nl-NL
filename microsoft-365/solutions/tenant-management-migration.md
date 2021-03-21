---
title: Stap 4. Migratie voor uw Microsoft 365 voor enterprise tenants
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
description: Migreert uw Windows-apparaten, Office-client-apps en Office-servers voor uw Microsoft 365-tenants.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929142"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 4. Migratie voor uw Microsoft 365 voor enterprise tenants

De meeste ondernemingsorganisaties hebben een heterogene omgeving met meerdere versies van besturingssystemen, clientsoftware en serversoftware. Microsoft 365 voor bedrijven bevat de veiligste versies van de belangrijkste onderdelen van uw IT-infrastructuur. Het bevat ook productiviteitsfuncties die zijn ontworpen om te profiteren van cloudtechnologieën.

Als u de zakelijke waarde van de geïntegreerde microsoft 365-suite met producten voor ondernemingen wilt maximaliseren, begint u met het plannen en implementeren van een strategie om deze releases te migreren:

| Van | Naar |
|:-------|:-----|
| Windows 7 en Windows 8.1 | Windows 10 Enterprise |
| Office-clientproducten geïnstalleerd op de apparaten van uw werknemer | Microsoft 365 Apps voor ondernemingen |
| Office-serverproducten geïnstalleerd op on-premises servers | Hun equivalente cloudservices in Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migreren naar Windows 10

Elke Microsoft 365 voor ondernemingslicentie bevat een licentie voor Windows 10 Enterprise. Als u uw apparaten met Windows 7 of Windows 8.1 wilt migreren, kunt u een in-place upgrade uitvoeren. Ondersteuning voor Windows 7 is beëindigd *op 14 januari 2020.* 

Zie Implementatiescenario's voor [Windows 10](/windows/deployment/windows-10-deployment-scenarios)voor meer methoden voor het installeren van Windows 10 Enterprise dan een in-place upgrade. U kunt ook zelf [de implementatie van Windows 10 plannen](/windows/deployment/planning/).

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migreren naar Microsoft 365 Apps voor bedrijven

Microsoft 365 voor bedrijven bevat Microsoft 365 Apps voor ondernemingen, een versie van de Office-clientproducten (Word, PowerPoint, Excel en Outlook) die is geïnstalleerd en bijgewerkt vanuit de Microsoft-cloud. Zie Over [Microsoft 365 Apps voor bedrijven voor meer informatie.](/deployoffice/about-microsoft-365-apps)

Ga als volgt te werk in plaats van uw computers actueel te houden voor Office 2019 of oudere versies:

1. Een Microsoft 365-licentie voor uw gebruikers aanvragen en toewijzen.
2. Verwijder Office 2013 of Office 2016 op hun computers.
3. Installeer Microsoft 365 Apps voor ondernemingen, afzonderlijk of tijdens een IT-implementatie. Zie Implementatiehandleiding [voor Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps)voor meer informatie.

Microsoft 365 Apps voor bedrijven installeert automatisch beveiligingsupdates en nieuwe functie-updates en kan profiteren van cloudservices in Microsoft 365 voor verbeterde beveiliging en productiviteit.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>On-premises servers en gegevens migreren naar Microsoft 365

Microsoft 365 voor bedrijven bevat cloudversies van Office-serverservices die gebruikmaken van enkele van dezelfde hulpprogramma's als on-premises versies van Office-serversoftware, zoals webbrowsers en de Outlook-client. Deze cloudservices worden automatisch bijgewerkt voor beveiliging en nieuwe functies. Na de migratie kan uw IT-afdeling de tijd besparen die nodig is om on-premises servers te onderhouden en bij te werken.

Gebruik de volgende bronnen voor informatie over het migreren van gebruikers en gegevens voor specifieke Microsoft 365-werkbelastingen:

- [Postvakken verplaatsen van on-premises Exchange Server naar Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [SharePoint-gegevens migreren van SharePoint Server naar SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Skype voor Bedrijven Online migreren naar Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Uw hele organisatie overzetten

Als u een beter beeld wilt krijgen van hoe u uw hele organisatie kunt verplaatsen naar de producten en services in Microsoft 365 voor bedrijven, downloadt u deze overgangsposter:

[![Afbeelding met de poster Overgang naar Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Deze poster van twee pagina‘s is een snelle manier om de bestaande infrastructuur te inventariseren. Gebruik deze informatie om richtlijnen te krijgen voor het over te gaan naar een product of service in Microsoft 365 voor bedrijven. Het toont Windows- en Office-producten en andere infrastructuur- en beveiligingselementen, zoals apparaatbeheer, identiteits- en bedreigingsbeveiliging en informatiebeveiliging en naleving.

## <a name="results-of-step-4"></a>Resultaten van stap 4

Voor migratie voor uw Microsoft 365-tenant hebt u het volgende bepaald:

- Op welke apparaten Windows 7 of Windows 8.1 wordt uitgevoerd en het plan om ze bij te werken naar Windows 10 Enterprise.
- Op welke apparaten worden de Office-client-apps uitgevoerd en het plan om deze bij te werken naar Microsoft 365-apps voor bedrijven.
- Welke on-premises Office-serverservices moeten worden gemigreerd naar hun Microsoft 365-equivalent en het plan om deze en hun gegevens te migreren.

Hier is een voorbeeld van een tenant met een voltooide migratie van on-premises servers.

![Voorbeeld van een tenant met een voltooide migratie van on-premises servers](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

In deze afbeelding heeft de organisatie:

- De on-premises Exchange Server-postvakken zijn gemigreerd naar Exchange Online.
- De on-premises SharePoint Server-sites en -gegevens zijn gemigreerd naar SharePoint in Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Doorlopend onderhoud voor migratie

Op permanente basis moet u mogelijk het volgende doen:

- Afhankelijk van de status van de migratie van uw Exchange-postvak, blijft u de overgang naar Exchange Online naar uw organisatie uitrollen.
- Afhankelijk van de status van uw on-premises SharePoint-sitemigratie, blijft u de overgang naar SharePoint in Microsoft 365 naar uw organisatie rollen.

## <a name="next-step"></a>Volgende stap

[![Stap 5. Apparaat- en app-beheer implementeren](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Ga verder [met apparaat- en app-beheer](tenant-management-device-management.md) om apparaat- en app-beheer te implementeren.