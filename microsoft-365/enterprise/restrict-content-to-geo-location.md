---
title: Inhoud van de SharePoint-site beperken tot een geografische locatie
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: In dit artikel leest u hoe u SharePoint-sites beperkt tot een opgegeven geografische locatie in een omgeving met meerdere geografische omgevingen.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689014"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Inhoud van de SharePoint-site beperken tot een geografische locatie

In sommige gevallen kunt u een site en de bestandsinhoud afdwingen om te zorgen dat de site is gemaakt op de geografische locatie waar de site is gemaakt, door te voorkomen dat de site wordt verplaatst of door te voorkomen dat de inhoud van de site in de cache wordt opgeslagen op een andere geografische locatie.

U kunt dit doen met behulp van de cmdlet [set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) en de **RestrictedToGeo** -parameter. Deze parameter heeft een standaardwaarde van NULL, maar u kunt deze wijzigen in een van de volgende opties:

|Scherp|Beschrijving|
|:----------|:----------|
|Geen beperking|De site kan worden verplaatst naar een andere geografische locatie.|
|BlockMoveOnly|Site kan niet worden verplaatst naar een andere geografische locatie, maar site-inhoud kan worden opgeslagen in een andere geografische locatie.|
|BlockFull|Site kan niet worden verplaatst naar een andere geografische locatie en de volledige inhoud van het bestand is niet in de cache opgeslagen in andere geografische locaties. De naam van een bestand (geoogst van de inhoud), de bestandsnaam en andere eigenschappen van het bestand, kan nog steeds in de cache voor andere geografische locaties worden opgeslagen.<br>Inhoud die is opgeslagen op de site voordat deze is geconfigureerd voor BlockFull, kan nog steeds in de cache zijn opgeslagen in andere geografische locaties.|

Gebruik de volgende syntaxis:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Bijvoorbeeld:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
