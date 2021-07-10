---
title: Multi-Geo-mogelijkheden in Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Meer informatie over hoe Teams werken met Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362651"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Multi-Geo-mogelijkheden in Microsoft Teams

Met multi-geo-mogelijkheden in Teams kunt Teams chatgegevens in rust opslaan op een opgegeven geografische locatie. Chatgegevens bestaan uit chatberichten, waaronder privéberichten, kanaalberichten en afbeeldingen die worden gebruikt in chats.

Teams gebruikt pdl (Preferred Data Location) voor gebruikers en groepen om te bepalen waar gegevens moeten worden opgeslagen. Als het PDF-nummer niet is ingesteld of ongeldig is, worden gegevens opgeslagen op de centrale locatie van de tenant.

## <a name="user-chat"></a>Gebruikerschat

Gebruikerschat bevat een-op-een-, een-op-veel- en privévergaderingsberichten.

Wanneer een nieuwe gebruiker wordt gemaakt, Teams de PDL van de gebruiker en slaat u al hun chatgegevens op die geografische locatie op.

Als een beheerder voor bestaande gebruikers de PDL voor een gebruiker toevoegt of wijzigt, worden de chatgegevens van die gebruiker toegevoegd aan een migratiewachtrij die moet worden verplaatst naar de opgegeven geografische locatie.

De opslaglocatie voor een een-op-een- of een-op-veel-chat is gebaseerd op de PDL van de persoon die de chat heeft gemaakt. Als de PDL van die gebruiker wordt gewijzigd, wordt de chat gemigreerd naar de nieuwe geografische locatie. De opslaglocatie voor een vergaderingschat is gebaseerd op de PDL van de organisator van de vergadering.

Als u de huidige locatie van de gegevens van een gebruiker wilt Teams, maakt u verbinding Teams [PowerShell en](/powershell/module/teams/connect-microsoftteams) voer u de volgende opdracht uit:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Kanaalberichten

Elke Microsoft 365 groep heeft een voorkeursgegevenslocatie (PDL) die de geografische locatie aanneert waar gerelateerde gegevens moeten worden opgeslagen. Teams gebruikt de PDL voor de groep die aan elk team is gekoppeld om te bepalen waar kanaalberichtengegevens voor dat team moeten worden opgeslagen. Dit geldt ook voor chat die plaatsvindt in een kanaalvergadering.

Wanneer een gebruiker een nieuw team maakt, bepaalt de PDL van die gebruiker welke PDL is toegewezen aan de Microsoft 365 groep. De groep PDL bepaalt waar de gegevens van dat team worden opgeslagen. Als de PDL van die gebruiker later wordt gewijzigd, wordt de PDL van de groep niet gewijzigd.

Als een beheerder voor bestaande teams de PDL toevoegt of wijzigt voor de Microsoft 365-groep die een team backt, worden de kanaalberichtengegevens van dat team toegevoegd aan een migratiewachtrij die moet worden verplaatst naar de opgegeven geografische locatie.

Als u de PDL van de Microsoft 365 groep verandert, worden Teams gegevens gemigreerd naar de gekozen locatie. De site of bestanden die aan de groep zijn gekoppeld, worden hierdoor SharePoint niet automatisch gemigreerd. U moet de site afzonderlijk verplaatsen door de procedures in Een site verplaatsen SharePoint naar een andere geografische locatie te [volgen.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) Zorg ervoor dat u beide stappen uit te voeren om te voorkomen dat Teams gegevens en SharePoint voor één groep op verschillende locaties.

Als u de huidige locatie van de gegevens van een team wilt vinden, maakt u [verbinding met Teams PowerShell](/powershell/module/teams/connect-microsoftteams) en voer u de volgende opdracht uit:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Gebruikerservaring

Teams Multi-Geo is naadloos voor de eindgebruiker. Nadat u het PDF-gegevensbestand van een gebruiker of een groep hebt gewijzigd, worden de betreffende gegevens in de wachtrij geplaatst voor de migratie en vindt de migratie automatisch plaats zonder gevolgen voor de gebruiker of de Teams-client, zelfs als deze actief is terwijl de migratie plaatsvindt.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Multi-Geo tenantconfiguratie](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Een multi-geo-omgeving beheren](administering-a-multi-geo-environment.md)

[Postvakken Exchange Online in een multi-geo-omgeving beheren](administering-exchange-online-multi-geo.md)
