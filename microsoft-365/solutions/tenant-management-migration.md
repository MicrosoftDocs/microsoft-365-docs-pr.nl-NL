---
title: Stap 4. Migratie voor uw Microsoft 365-tenants voor ondernemingen
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
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406358"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 4. Migratie voor uw Microsoft 365-tenants voor ondernemingen

De meeste ondernemingen hebben een heterogene omgeving met meerdere versies van besturingssystemen, clientsoftware en serversoftware. Microsoft 365 voor Ondernemingen bevat de veiligste versies van de belangrijkste onderdelen van uw IT-infrastructuur. Het bevat ook productiviteitsfuncties die zijn ontworpen om te profiteren van cloudtechnologieën.

Als u de zakelijke waarde van de geïntegreerde suite met Microsoft 365 enterprise-producten wilt maximaliseren, begint u met het plannen en implementeren van een strategie voor het migreren van deze releases:

| Van | Naar |
|:-------|:-----|
| Windows 7 en Windows 8.1 | Windows 10 Enterprise |
| Office-clientproducten geïnstalleerd op de apparaten van de werknemer | Microsoft 365-apps voor ondernemingen |
| Office Server-producten geïnstalleerd op on-premises servers | De overeenkomstige cloudservices in Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migreren naar Windows 10

Elke Microsoft 365 Enterprise-licentie bevat een licentie voor Windows 10 Enterprise. Als u uw apparaten met Windows 7 of Windows 8.1 wilt migreren, kunt u een in-place upgrade uitvoeren. Ondersteuning voor Windows 7 is beëindigd op *14 januari 2020.* 

Zie windows 10-implementatiescenario's voor aanvullende methoden voor het installeren van Windows [10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)Enterprise voorbij een in-place upgrade. U kunt ook zelf [de implementatie van Windows 10 plannen](https://aka.ms/planforwin10deployment).

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migreren naar Microsoft 365-apps voor ondernemingen

Microsoft 365 voor ondernemingen omvat Microsoft 365-apps voor ondernemingen, een versie van de Office-clientproducten (Word, PowerPoint, Excel en Outlook) die wordt geïnstalleerd en bijgewerkt vanuit de Microsoft-cloud. Zie Voor meer informatie over [Microsoft 365-apps voor ondernemingen.](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)

In plaats van de computers actueel te houden voor Office 2019 of oudere versies, volgt u de volgende stappen:

1. Haal een Microsoft 365-licentie op en wijs deze toe voor uw gebruikers.
2. Verwijder Office 2013 of Office 2016 van hun computers.
3. Installeer Microsoft 365 Apps voor ondernemingen afzonderlijk of tijdens een IT-implementatie. Zie de implementatiehandleiding [voor Microsoft 365-apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)voor meer informatie.

Microsoft 365 Apps voor ondernemingen installeert beveiligingsupdates en nieuwe functie-updates automatisch en kan profiteren van cloudservices in Microsoft 365 voor betere beveiliging en productiviteit.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>On-premises servers en gegevens migreren naar Microsoft 365

Microsoft 365 voor Ondernemingen bevat cloudversies van Office-serverservices die gebruikmaken van een aantal dezelfde hulpprogramma's als on-premises versies van Office Server-software, zoals webbrowsers en de Outlook-client. Deze cloudservices worden automatisch bijgewerkt voor beveiliging en nieuwe functies. Na de migratie kan uw IT-afdeling de tijd besparen die nodig is om on-premises servers te onderhouden en bij te werken.

Gebruik de volgende bronnen voor informatie over het migreren van gebruikers en gegevens voor specifieke Microsoft 365-werkbelastingen:

- [Postvakken verplaatsen van on-premises Exchange Server naar Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [SharePoint-gegevens migreren van SharePoint Server naar SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [Skype voor Bedrijven Online migreren naar Microsoft Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Uw hele organisatie overzetten

Download deze overgangsposter voor een beter beeld van hoe u uw hele organisatie kunt verplaatsen naar de producten en services in Microsoft 365 enterprise:

[![Afbeelding met de poster Overgang naar Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Deze poster van twee pagina‘s is een snelle manier om de bestaande infrastructuur te inventariseren. Gebruik deze voor hulp bij het over overstapen naar een product of service in Microsoft 365 voor Ondernemingen. Het toont Windows- en Office-producten en andere infrastructuur- en beveiligingselementen, zoals apparaatbeheer, identiteits- en bedreigingsbescherming, en informatiebescherming en naleving.

## <a name="results-of-step-4"></a>Resultaten van stap 4

Voor de migratie van uw Microsoft 365-tenant hebt u het volgende bepaald:

- Op welke apparaten Windows 7 of Windows 8.1 wordt uitgevoerd en van plan zijn deze bij te werken naar Windows 10 Enterprise.
- Op welke apparaten de Office-client-apps worden uitgevoerd en welke van plan zijn ze bij te werken naar Microsoft 365-apps voor ondernemingen.
- Welke on-premises Office-serverservices moeten worden gemigreerd naar het equivalent van Microsoft 365 en welke services en hun gegevens moeten worden gemigreerd.

Hier is een voorbeeld van een tenant met een voltooide migratie van on-premises servers.

![Voorbeeld van een tenant met een voltooide migratie van on-premises servers](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

In deze afbeelding heeft de organisatie het volgende:

- De on-premises Exchange Server-postvakken zijn gemigreerd naar Exchange Online.
- De on-premises SharePoint Server-sites en -gegevens zijn gemigreerd naar SharePoint in Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Doorlopend onderhoud voor migratie

Oplopende basis moet u mogelijk het volgende doen:

- Afhankelijk van de status van de migratie van uw Exchange-postvak, blijft u de overgang naar Exchange Online naar uw organisatie rollen.
- Afhankelijk van de status van de migratie van uw on-premises SharePoint-site, blijft u de overgang naar SharePoint in Microsoft 365 naar uw organisatie rollen.

## <a name="next-step"></a>Volgende stap

[![Stap 5. Apparaat- en app-beheer implementeren](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Ga verder [met apparaat- en app-beheer](tenant-management-device-management.md) om apparaat- en app-beheer te implementeren.
