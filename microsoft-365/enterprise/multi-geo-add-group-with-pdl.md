---
title: Een Microsoft 365-groep maken met een specifieke PDL
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Meer informatie over het maken van een Microsoft 365-groep met een opgegeven voorkeursgegevenslocatie in een multi-geoomgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923742"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Een Microsoft 365-groep maken met een specifieke PDL

Wanneer gebruikers in een multi-geo-omgeving een Microsoft 365-groep maken, wordt de gewenste gegevenslocatie van de groep automatisch ingesteld op die van de gebruiker. Globale, SharePoint- en Exchange-beheerders kunnen groepen maken in elke regio die ze selecteren. 

Als u een groep met een specifieke PDL wilt maken, kunt u dat doen via het SharePoint-beheercentrum of via de Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdlet. Wanneer u dit doet, worden zowel het groepspostvak als de SharePoint-site die aan de groep is gekoppeld, ingericht in het opgegeven PDL.

Als u een Microsoft 365-groep wilt maken met de PDL die u opgeeft, gaat u naar het SharePoint-beheercentrum op de geografische locatie waar u de groepssite wilt maken.

Bijvoorbeeld:

Als u een groepssite wilt maken op uw locatie in Australië, kunt u naar https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Selecteer **+ Maken.**
2. Volg het proces om een groepssite te maken.

Uw groepssite wordt ingericht op de geografische locatie die overeenkomt met het SharePoint-beheercentrum waaruit u de aanvraag voor het maken van de site hebt gestart. 

Exchange PowerShell gebruiken 

Maak verbinding met Exchange Online PowerShell en passeert de parameter *-MailBoxRegion* met de geolocatiecode.

Bijvoorbeeld: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Schermafbeelding van New-UnifiedGroup PowerShell-cmdlet met syntaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

SharePoint group site provisioning is on-demand. De site wordt ingericht de eerste keer dat een groepseigenaar of lid toegang tot de site probeert te krijgen.

## <a name="geo-location-codes"></a>Geolocatiecodes

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Verwante onderwerpen

[Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)