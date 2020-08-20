---
title: Een interne beheerder overnemen
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Meer informatie over hoe u uw e-mailadres en domein eigendom controleert voor het overnemen van een niet-beheerde Tenant in Microsoft 365
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814466"
---
# <a name="perform-an-internal-admin-takeover"></a>Een interne beheerder overnemen

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 

Als u een beheerder bent en een niet-beheerde Tenant die is gemaakt door een selfservicegebruiker, wilt overnemen, kunt u dit doen met een interne beheerder van de beheerder.

> [!NOTE]
> Een selfservice registratie voor een cloudservice waarin Azure AD wordt gebruikt, voegt de gebruiker toe aan een niet-beheerde of ' schaduw ' Azure AD-Directory en maak een niet-beheerde Tenant. Een niet-beheerde Tenant is een adreslijst zonder globale beheerder. Als u wilt weten of een Tenant wordt beheerd of niet beheerd, raadpleegt u [Tenant type bepalen](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Stap 1: uw e-mailadres verifiëren

> [!NOTE]
> Als selfservice in de Tenant is ingeschakeld, kunnen gebruikers zich zelf abonneren op gratis services, zoals Power BI. Bij deze stappen wordt ervan uitgegaan dat een selfservicegebruikers abonnement de niet-beheerde Tenant heeft gemaakt die u wilt overnemen van de beheerder. Wanneer u in de eerste stap een gebruikerscontext maakt in de niet-beheerde Tenant, maakt u gebruik van Power BI om het pad van de beheerder te illustreren.

1. Als u zich wilt registreren voor Power bi, gaat u naar de [Power bi-site](https://powerbi.com) en selecteert u **gratis**  >  **proefversie** starten (in delen met Power bi Pro box). 

2. Meld u aan met een gebruikersaccount dat gebruikmaakt van de domeinnaam van uw organisatie (zoals `powerbiadmin@contoso.com` ). Als uw account al wordt gebruikt, meldt u zich aan met uw huidige wachtwoord.

3. Controleer uw e-mailadres op de **verificatiecode** en voer de code in om uw e-mailadres te valideren.
    
## <a name="step-2-create-a-new-account"></a>Stap 2: een nieuw account maken

1. Wanneer u de verificatiecode invoert, wordt u overgezet naar een pagina waar u een nieuw account kunt maken. 
    
2. Vul de velden gebruikersnaam en wachtwoord in met het account dat u wilt gebruiken en selecteer **starten**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Stap 3: het eigendom van het domein verifiëren en de beheerder worden

1. De wizard wordt **de beheerder worden** geopend. Als de wizard niet start, zoekt u de tegel **beheerder** en selecteert u deze. 

2. Selecteer **Ja, ik wil de beheerder zijn**.

3. Zorg dat u eigenaar bent van het domein dat u wilt overnemen door een TXT-record toe te voegen aan uw domeinregistratie. Met de wizard kunt u de toe te voegen TXT-record, en een koppeling naar de website van uw registratie, en een koppeling naar stapsgewijze instructies weergeven.
    
4. Wanneer u de TXT-record hebt toegevoegd aan de registratie site, gaat u terug naar de wizard en selecteert u **OK, ik heb de record toegevoegd**.
    
> [!NOTE]
> Het overnemen van de Shadow-Tenant heeft geen gevolgen voor bestaande informatie of services. Maar als gebruikers in het domein zich hebben geregistreerd voor services waarvoor een licentie is vereist, wordt u gevraagd om licenties voor hen te kopen als onderdeel van het overnemen van de beheerdersrol. U kunt licenties kopen of verwijderen nadat het installatieproces van de beheerder is voltooid.
  
## <a name="related-articles"></a>Verwante artikelen

YouTube: [3 stappen voor het overnemen van een IT-beheerder voor Power bi en Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Beheerders overname in azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Zelfregistratie gebruiken in uw organisatie](self-service-sign-up.md)
  
[Wat is de rol van de Power BI-servicebeheerder?](https://docs.microsoft.com/power-bi/service-admin-role)

