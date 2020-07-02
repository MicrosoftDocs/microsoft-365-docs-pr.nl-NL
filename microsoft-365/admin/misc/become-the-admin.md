---
title: Een interne beheerdersovername uitvoeren
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
description: Meer informatie over het verifiëren van uw e-mail- en domeineigendom om een niet-beheersde tenant over te nemen in Microsoft 365
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022155"
---
# <a name="perform-an-internal-admin-takeover"></a>Een interne beheerdersovername uitvoeren

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 

Als u een beheerder bent en een onbeheerde tenant wilt overnemen die is gemaakt door een aanmelding van een selfservicegebruiker, u dit doen met een interne beheerdersovername.

> [!NOTE]
> Een selfservice-aanmelding voor elke cloudservice die Azure AD gebruikt, voegt de gebruiker toe aan een onbeheerde of 'schaduw'-Azure AD-map en maakt een onbeheerde tenant. Een onbeheerde tenant is een map zonder globale beheerder. Zie [Tenanttype bepalen](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)als u wilt bepalen of een tenant wordt beheerd of niet wordt beheerd. 
  
## <a name="step-1-verify-your-email-address"></a>Stap 1: Uw e-mailadres verifiëren

> [!NOTE]
> Als selfservice is ingeschakeld in uw tenant, kunnen gebruikers zich op eigen houtje abonneren op gratis services, zoals Power BI. In deze stappen wordt ervan uitgegaan dat een selfservice-gebruikersabonnement de onbeheerde tenant heeft gemaakt die u als beheerder wilt overnemen. In de eerste stap maakt u een gebruikerscontext in de onbeheerde tenant en gebruikt u Power BI om het overnamepad voor beheerders te illustreren.

1. Als u zich wilt aanmelden voor Power BI, gaat u naar de [Power BI-site](https://powerbi.com) en **selecteert**u  >  **Gratis start-proefperiode** starten (in het vak Delen met Power BI Pro). 

2. Meld u aan met een gebruikersaccount dat de domeinnaam van uw organisatie gebruikt (zoals `powerbiadmin@contoso.com` ). Als uw account al in gebruik is, meldt u zich aan met uw huidige wachtwoord.

3. Controleer uw e-mail op de **verificatiecode** en voer de code in om uw e-mailadres te valideren.
    
## <a name="step-2-create-a-new-account"></a>Stap 2: Een nieuw account maken

1. Wanneer u de verificatiecode invoert, wordt u naar een pagina gebracht waar u een nieuw account maken. 
    
2. Vul de gebruikersnaam- en wachtwoordvelden in met het account dat u wilt gebruiken en selecteer **Start**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Stap 3: Domeineigendom verifiëren en beheerder worden

1. De wizard **De beheerder worden** wordt geopend. Als de wizard niet wordt gestart, zoekt u naar de tegel **Beheerder** en selecteert u deze. 

2. Selecteer **Ja, ik wil de beheerder zijn.**

3. Controleer of u eigenaar bent van het domein dat u wilt overnemen door een TXT-record toe te voegen aan uw domeinregistrar. De wizard geeft u de TXT-record toe te voegen, evenals een link naar de website van uw registrar, en een link naar stapsgewijze instructies.
    
4. Zodra u de TXT-record aan uw registrar-site hebt toegevoegd, keert u terug naar de wizard en selecteert **u Oke, ik heb de record toegevoegd.**
    
> [!NOTE]
> De overname van de schaduw tenant heeft geen invloed op bestaande informatie of diensten. Als gebruikers in het domein zich echter hebben aangemeld voor services waarvoor een licentie vereist is, wordt u gevraagd om licenties voor hen te kopen als onderdeel van de overname van de beheerdersrol. U licenties kopen of verwijderen zodra het installatieproces voor beheerders is voltooid.
  
## <a name="related-articles"></a>Verwante artikelen

YouTube: 3 stappen om een OVERNAME van [IT-beheerders voor Power BI en Microsoft 365 te doen](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Beheerdersovername in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Hulp krijgen bij domeinen](../get-help-with-domains/get-help-with-domains.md)

[Selfservice-aanmelding gebruiken in uw organisatie](self-service-sign-up.md)
  
[Inzicht in de functie Power BI-servicebeheerder](https://docs.microsoft.com/power-bi/service-admin-role)

