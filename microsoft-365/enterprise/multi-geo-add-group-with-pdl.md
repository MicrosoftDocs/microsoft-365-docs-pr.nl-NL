---
title: Een Microsoft 365-groep met een specifieke PDL maken
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
description: Meer informatie over het maken van een Microsoft 365-groep met een opgegeven voorkeurs gegevenslocatie in een omgeving met meerdere geografische locaties.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906d0b4881dd69bbf47cbb536c6c448a1a4f611
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689267"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Een Microsoft 365-groep met een specifieke PDL maken

Wanneer gebruikers in een omgeving met meerdere geografische groepen een Microsoft 365-groep maken, wordt de gewenste gegevenslocatie van de groep automatisch ingesteld op die van de gebruiker. Globaal, SharePoint-en Exchange-beheerders kunnen groepen maken in elk gebied dat ze selecteren. 

Als u een groep met een specifieke PDL moet maken, kunt u dat doen via het SharePoint-Beheercentrum of via de Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdlet. Wanneer u dit doet, wordt het postvak van de groep en de SharePoint-site die aan de groep zijn gekoppeld, ingericht in de opgegeven PDL.

Als u een Microsoft 365-groep wilt maken met de PDL die u opgeeft, gaat u naar het SharePoint-Beheercentrum op de geografische locatie waar u de groepssite wilt maken.

Bijvoorbeeld:

Als u een groepssite wilt maken op uw Australische locatie, kunt u naar https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Selecteer **+ maken**.
2. Volg het proces voor het maken van een groepssite.

Uw groepssite wordt ingericht op de geografische locatie van het SharePoint-Beheercentrum waarvan u het maken van sites hebt gestart. 

Exchange PowerShell gebruiken 

Maak verbinding met Exchange Online PowerShell en geef de parameter *-MailBoxRegion* door de geo-vestigingscode.

Bijvoorbeeld: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Schermafbeelding van een PowerShell-cmdlet New-UnifiedGroup met syntaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

Houd er rekening mee dat het inrichten van SharePoint-groeps sites op aanvraag is. De site wordt ingericht wanneer een groepseigenaar of lid de eerste keer probeert toegang te krijgen tot de site.

## <a name="geo-location-codes"></a>Geo-vestigingscodes

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Verwante onderwerpen

[Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
