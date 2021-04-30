---
title: Een groep Microsoft 365 maken met een specifieke voorkeursgegevenslocatie
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
description: Meer informatie over het maken Microsoft 365 groep met een opgegeven voorkeursgegevenslocatie in een multi-geo-omgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086821"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>Een groep Microsoft 365 maken met een specifieke voorkeursgegevenslocatie

Wanneer gebruikers in een multi-geo-omgeving een Microsoft 365 Groep maken, wordt de voorkeurslocatie voor gegevens van de groep automatisch ingesteld op die van de gebruiker. Globale, SharePoint en Exchange Beheerders kunnen groepen maken in elke regio die ze selecteren. 

Als u een groep met een specifiek PDF-programma wilt maken, kunt u dat doen via het SharePoint-beheercentrum of via de microsoft PowerShell Exchange Online New-UnifiedGroup-cmdlet. Wanneer u dit doet, worden zowel het groepspostvak als de SharePoint gekoppeld aan de groep ingericht in het opgegeven PDL.

Als u een Microsoft 365 groep wilt maken met de PDL die u opgeeft, gaat u naar het SharePoint-beheercentrum op de geografische locatie waar u de groepssite wilt maken.

Bijvoorbeeld:

Als u een groepssite wilt maken op uw locatie in Australië, kunt u naar https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Selecteer **+ Maken.**
2. Volg het proces om een groepssite te maken.

Uw groepssite wordt ingericht op de geografische locatie die overeenkomt met het SharePoint beheercentrum waaruit u de aanvraag voor het maken van de site hebt gestart. 

PowerShell Exchange gebruiken 

Verbinding maken powershell Exchange Online en passeert u de parameter *-MailBoxRegion* met de geolocatiecode.

Bijvoorbeeld: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Schermafbeelding van New-UnifiedGroup PowerShell-cmdlet met syntaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

Houd er rekening SharePoint groepssite-inrichting op aanvraag is. De site wordt ingericht de eerste keer dat een groepseigenaar of lid toegang tot de site probeert te krijgen.

## <a name="geo-location-codes"></a>Geolocatiecodes

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Verwante onderwerpen

[Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)
