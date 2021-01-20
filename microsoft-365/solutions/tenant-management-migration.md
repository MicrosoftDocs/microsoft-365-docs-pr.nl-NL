---
title: Stap 4. Migratie voor uw Microsoft 365 for Enterprise-tenants
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
description: Migreer uw Windows-apparaten, Office-client-apps en Office-servers voor uw Microsoft 365-tenants.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908528"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 4. Migratie voor uw Microsoft 365 for Enterprise-tenants

De meeste Enterprise-organisaties hebben een heterogene omgeving met verschillende versies van besturingssystemen, clientsoftware en serversoftware. Microsoft 365 voor Enterprise bevat de veiligste versies van de belangrijkste onderdelen van de IT-infrastructuur. Dit omvat ook productiviteitsfuncties die zijn ontworpen om te profiteren van Cloud technologieën.

Als u de Business waarde van de Microsoft 365 for Enterprise Integrated suite van producten wilt maximaliseren, begint u met het plannen en implementeren van een strategie voor het migreren van de volgende versies:

| Van | Naar |
|:-------|:-----|
| Windows 7 en Windows 8,1 | Windows 10 Enterprise |
| Office-clientproducten die zijn geïnstalleerd op de apparaten van de werknemers | Microsoft 365-apps voor ondernemingen |
| Office Server-producten die zijn geïnstalleerd op on-premises servers | De equivalente cloudservices in Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migreren naar Windows 10

Elke Microsoft 365 for Enterprise-licentie bevat een licentie voor Windows 10 Enterprise. Voor het migreren van apparaten met Windows 7 of Windows 8,1 kunt u een interne upgrade uitvoeren. Ondersteuning beëindigd voor Windows 7 op *14 januari 2020*. 

Zie [Windows 10-implementatiescenario's](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)voor meer informatie over het installeren van een upgrade naar Windows 10 Enterprise na een interne upgrade. U kunt ook zelf [de implementatie van Windows 10 plannen](https://aka.ms/planforwin10deployment).

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrating to Microsoft 365 apps for Enterprise

Microsoft 365 voor Enterprise omvat Microsoft 365-apps voor Enterprise, een versie van de Office-clientproducten (Word, PowerPoint, Excel en Outlook) die is geïnstalleerd en bijgewerkt met de Microsoft-Cloud. Zie [over Microsoft 365-apps voor ondernemingen voor](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)meer informatie.

Voer de volgende stappen uit in plaats van dat u de computer up-to-date hoeft te houden voor Office 2019 of eerdere versies:

1. Een Microsoft 365-licentie voor uw gebruikers aan te schaffen en toe te wijzen.
2. Verwijder Office 2013 of Office 2016 op hun computer.
3. Installeer Microsoft 365-apps voor Enterprise, afzonderlijk of tijdens een IT-implementatie. Zie [Implementatiehandleiding voor Microsoft 365-apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)voor meer informatie.

Microsoft 365-apps for Enterprise installeert zowel beveiligingsupdates als nieuwe functie updates en kan gebruikmaken van cloudservices in Microsoft 365 voor uitgebreide beveiliging en productiviteit.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>On-premises servers en gegevens migreren naar Microsoft 365

Microsoft 365 voor Enterprise bevat Cloud versies van Office Server-services die gebruikmaken van enkele van deze hulpprogramma's als on-premises versies van Office Server-software, zoals webbrowsers en de Outlook-client. Deze services op de cloud worden automatisch bijgewerkt voor beveiliging en nieuwe functies. Na de migratie kan de IT-afdeling de tijd besparen die het duurt om on-premises servers te onderhouden en bij te werken.

Gebruik de volgende bronnen voor meer informatie over het migreren van gebruikers en gegevens voor specifieke Microsoft 365-werkbelasting:

- [Postvakken verplaatsen van on-premises Exchange-Server naar Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [SharePoint-gegevens van SharePoint Server migreren naar SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [Skype voor bedrijven online migreren naar Microsoft teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Uw hele organisatie overzetten

Als u een betere afbeelding wilt over het verplaatsen van de hele organisatie naar de producten en services in Microsoft 365 for Enterprise, downloadt u deze overgangs poster:

[![Afbeelding met de overgang naar Microsoft 365-poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Deze poster van twee pagina‘s is een snelle manier om de bestaande infrastructuur te inventariseren. U kunt deze gebruiken voor informatie over het overstappen op een product of service in Microsoft 365 for Enterprise. Er worden Windows-en Office-producten en andere infrastructuur en beveiligingselementen weergegeven, zoals Apparaatbeheer, identiteit en beveiliging van bedreigingen, en gegevensbescherming en compliance.

## <a name="results-of-step-4"></a>Resultaten van stap 4

Voor migratie van uw Microsoft 365-Tenant hebt u het volgende vastgesteld:

- Op welke apparaten wordt Windows 7 of Windows 8,1 en het abonnement voor het bijwerken naar Windows 10 Enterprise geactiveerd.
- 365 op welke apparaten worden de Office-client-apps en het abonnement voor het bijwerken van de Office-client apps voor Enterprise gebruikt.
- Welke on-premises Office Server-services moeten worden gemigreerd naar het equivalent van Microsoft 365 en de planning voor het migreren van hun gegevens.

Hier ziet u een voorbeeld van een Tenant met een voltooide migratie van on-premises servers.

![Voorbeeld van een Tenant met een voltooide migratie van on-premises servers](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

In deze afbeelding is de organisatie:

- De on-premises Exchange-Server postvakken gemigreerd naar Exchange Online.
- Gemigreerde on-premises SharePoint Server-sites en-gegevens naar SharePoint in Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Voortdurende onderhoud voor migratie

Het kan zijn dat u het volgende moet doen:

- Afhankelijk van de status van uw Exchange-postvak migratie gaat u verder met het migreren van de overgang naar Exchange Online naar uw organisatie.
- Afhankelijk van de status van uw on-premises SharePoint-sitemigratie gaat u verder met de overgang naar SharePoint in Microsoft 365 naar uw organisatie.

## <a name="next-step"></a>Volgende stap

[![Stap 5. Apparaten en app-beheer implementeren](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Ga verder met [apparaat en app-beheer](tenant-management-device-management.md) om apparaat-en app-beheer te implementeren.
