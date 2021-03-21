---
title: Microsoft 365 multi-geo eDiscovery configureren
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Lees hoe u de parameter Regio kunt gebruiken om eDiscovery te configureren voor gebruik op satellietlocaties in Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923718"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo eDiscovery-configuratie

[Met geavanceerde eDiscovery-mogelijkheden](../compliance/overview-ediscovery-20.md) kan een beheerder van multi-geo eDiscovery alle geografische gegevens doorzoeken zonder dat u een beveiligingsfilter 'Regio' hoeft te gebruiken. Gegevens worden geëxporteerd naar het Azure-exemplaar van de centrale locatie van de multi-geo tenant. 

Zonder geavanceerde eDiscovery-mogelijkheden kan een eDiscovery-manager of beheerder van een multi-geoten tenant eDiscovery alleen uitvoeren op de centrale locatie van die tenant. Ter ondersteuning van de mogelijkheid om eDiscovery uit te voeren voor satellietlocaties, is een nieuwe parameter voor compliancebeveiligingsfilter 'Regio' beschikbaar via PowerShell. Deze parameter kan worden gebruikt door tenants waarvan de centrale locatie zich in Noord-Amerika, Europa of Azië en de Stille Oceaan bevindt. Geavanceerde eDiscovery wordt aanbevolen voor tenants waarvan de centrale locatie zich niet in Noord-Amerika, Europa of Azië-Pacific bevindt en die eDiscovery moeten uitvoeren op satellietlocatielocaties. 

De globale beheerder van Microsoft 365 moet eDiscovery Manager-machtigingen toewijzen om anderen toe te staan eDiscovery uit te voeren en een parameter 'Regio' toe te wijzen in het toepasselijke compliancebeveiligingsfilter om de regio voor het uitvoeren van eDiscovery op te geven als satellietlocatie, anders wordt er geen eDiscovery uitgevoerd voor de satellietlocatie.

Wanneer de rol eDiscovery Manager of Beheerder is ingesteld voor een bepaalde satellietlocatie, kan eDiscovery Manager of Beheerder alleen eDiscovery-zoekacties uitvoeren op de SharePoint-sites en OneDrive-sites op die satellietlocatie. Als een eDiscovery Manager of Beheerder probeert te zoeken op SharePoint- of OneDrive-sites buiten de opgegeven satellietlocatie, worden er geen resultaten geretourneerd. Wanneer de eDiscovery Manager of Beheerder voor een satellietlocatie een export activeert, worden gegevens ook geëxporteerd naar het Azure-exemplaar van die regio. Dit helpt organisaties om aan de naleving te blijven voldoen door niet toe te staan dat inhoud wordt geëxporteerd over gecontroleerde randen.

> [!NOTE]
> Als een eDiscovery Manager moet zoeken op meerdere SharePoint-satellietlocaties, moet er een ander gebruikersaccount worden gemaakt voor eDiscovery Manager, dat de alternatieve satellietlocatie aangeeft waar de OneDrive- of SharePoint-sites zich bevinden.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Het beveiligingsfilter voor naleving voor een regio instellen:

1. [Verbinding maken met Microsoft 365 Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. Gebruik de volgende syntaxis:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Bijvoorbeeld:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Zie het [artikel New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) voor aanvullende parameters en syntaxis.