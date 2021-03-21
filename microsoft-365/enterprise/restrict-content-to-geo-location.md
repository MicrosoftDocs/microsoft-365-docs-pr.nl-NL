---
title: Inhoud van SharePoint-site beperken tot een geografische locatie
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
description: In dit artikel leert u hoe u SharePoint-sites kunt beperken tot een opgegeven geografische locatie in een multi-geoomgeving.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927262"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Inhoud van SharePoint-site beperken tot een geografische locatie

In sommige gevallen kunt u ervoor kiezen om een site en de bestandsinhoud ervan af te dwingen op de geografische locatie waar de site is gemaakt, door te voorkomen dat de site wordt verplaatst of door te voorkomen dat de bestandsinhoud van de site op een andere geografische locatie wordt ingeslagen.

U kunt dit doen met de [cmdlet Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) met de **parameter RestrictedToGeo.** Deze parameter heeft een standaardwaarde van NULL, maar u kunt deze wijzigen in een van de volgende opties:

|Beperking|Beschrijving|
|:----------|:----------|
|NoRestriction|De site kan worden verplaatst naar een andere geografische locatie.|
|BlockMoveOnly|Site kan niet worden verplaatst naar een andere geografische locatie, maar site-inhoud kan in de cache worden opgeslagen op andere geografische locaties.|
|BlockFull|Site kan niet worden verplaatst naar een andere geografische locatie en volledige bestandsinhoud wordt niet in de cache op andere geografische locaties opgeslagen. De titel van bestanden (afkomstig van de inhoud), de bestandsnaam en andere eigenschappen van het bestand kunnen nog steeds in de cache worden opgeslagen op andere geografische locaties.<br>Inhoud die is opgeslagen op de site voordat deze is geconfigureerd voor BlockFull, blijft mogelijk in de cache op andere geografische locaties.|

Gebruik de volgende syntaxis:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Bijvoorbeeld:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`