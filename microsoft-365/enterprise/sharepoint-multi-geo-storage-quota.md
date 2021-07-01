---
title: SharePoint opslagquota in multi-geo-omgevingen
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
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Meer informatie SharePoint opslagquota's in multi-geoomgevingen en hoe quota's kunnen worden beheerd door de SharePoint Online-beheerder.
ms.openlocfilehash: 0843407e7926027e28cdd1f5893c4aafec4e1cd5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230089"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>SharePoint opslagquota in multi-geo-omgevingen

Standaard delen alle geografische locaties van een multi-geo-omgeving het beschikbare opslagquotum voor tenants.

Met de SharePoint voor geografische opslagquota kunt u het opslagquotum voor elke geografische locatie beheren. Wanneer u een opslagquotum toewijst voor een geografische locatie, wordt dit de maximale hoeveelheid opslagruimte die beschikbaar is voor die geografische locatie en wordt deze afgetrokken van het beschikbare tenantopslagquotum. Het resterende beschikbare tenantopslagquotum wordt vervolgens gedeeld over de geconfigureerde geografische locaties waarvoor geen specifiek opslagquotum is toegewezen.

Het SharePoint opslagquotum voor elke geografische locatie kan worden toegewezen door de SharePoint Online-beheerder door verbinding te maken met de centrale locatie. Geobeheerders voor satellietlocaties kunnen het opslagquotum bekijken, maar kunnen het niet toewijzen.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Een opslagquotum configureren voor een geografische locatie

Gebruik de [Microsoft Office SharePoint Online module en](https://www.microsoft.com/download/details.aspx?id=35588) maak verbinding met de centrale locatie om het opslagquotum voor een geografische locatie toe te wijzen.

Als u een Storage quota voor een locatie wilt toewijzen, moet u cmdlet uitvoeren:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Als u Storage quotum voor de huidige geografische locatie wilt weergeven, gaat u als volgende te werk:

```powershell
Get-SPOGeoStorageQuota
```

![Schermafbeelding van PowerShell-venster met Get-SPOGeoStorageQuota cmdlet](../media/multi-geo-storage-quota.png)

Als u de Storage voor alle geografische locaties wilt weergeven, gaat u als volgende te werk:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

Als u het toegewezen opslagquotum voor een geografische locatie wilt verwijderen, stelt u `StorageQuota value = 0` het volgende in:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```
