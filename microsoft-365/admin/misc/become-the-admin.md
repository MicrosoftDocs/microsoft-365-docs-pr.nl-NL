---
title: Een interne beheerdersovername uitvoeren
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Informatie over het verifiëren van uw e-mail- en domeineigenschap om een niet-beherende tenant over te nemen in Microsoft 365
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914844"
---
# <a name="perform-an-internal-admin-takeover"></a>Een interne beheerdersovername uitvoeren

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 

Als u een beheerder bent en een niet-beheerde tenant wilt overnemen die is gemaakt door een selfservicegebruiker, kunt u dit doen met een interne beheerdersovername.

> [!NOTE]
> Een selfservice-aanmelding voor een cloudservice die Azure AD gebruikt, voegt de gebruiker toe aan een niet-beheerde of 'schaduw' Azure AD-adreslijst en maakt een niet-beheerde tenant. Een niet-beheerde tenant is een adreslijst zonder globale beheerder. Zie Tenanttype bepalen om te bepalen of een tenant wordt beheerd of niet wordt [beheerd.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>Stap 1: Uw e-mailadres verifiëren

> [!NOTE]
> Als selfservice is ingeschakeld in uw tenant, kunnen gebruikers zich zelf abonneren op gratis services, zoals Power BI. In deze stappen wordt ervan uitgenomen dat een selfservicegebruikerabonnement de niet-beheerde tenant heeft gemaakt die u als beheerder wilt overnemen. In de eerste stap maakt u een gebruikerscontext in de niet-beheerde tenant en gebruikt u Power BI om het overnamepad van de beheerder te illustreren.

1. Als u zich wilt registreren voor Power BI, gaat u naar de [Power BI-site](https://powerbi.com) en **selecteert** u Gratis proefabonnement starten (in het vak Delen  >   met Power BI Pro). 

2. Meld u aan met een gebruikersaccount dat de domeinnaam van uw organisatie gebruikt (zoals `powerbiadmin@contoso.com` ). Als uw account al in gebruik is, meld u dan aan met uw huidige wachtwoord.

3. Controleer uw e-mail op **de verificatiecode** en voer de code in om uw e-mailadres te valideren.
    
## <a name="step-2-create-a-new-account"></a>Stap 2: Een nieuw account maken

1. Wanneer u de verificatiecode in typt, wordt u naar een pagina gebracht waar u een nieuw account kunt maken. 
    
2. Vul de velden gebruikersnaam en wachtwoord in met het account dat u wilt gebruiken en selecteer **Vervolgens Start.** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Stap 3: Domeineigenschap verifiëren en beheerder worden

1. De **wizard Word de beheerder** wordt geopend. Als de wizard niet wordt start, gaat u naar de tegel **Beheerder** en selecteert u deze. 

2. Selecteer **Ja, ik wil de beheerder zijn.**

3. Controleer of u de eigenaar bent van het domein dat u wilt overnemen door een TXT-record toe te voegen aan uw domeinregistrar. De wizard geeft u de TXT-record die u wilt toevoegen, evenals een koppeling naar de website van uw registrar en een koppeling naar stapsgewijs instructies.
    
4. Nadat u de TXT-record hebt toegevoegd aan uw registrarsite, gaat u terug naar de wizard en selecteert u **Ok, ik heb de record toegevoegd.**
    
> [!NOTE]
> Het overnemen van de schaduw tenant heeft geen invloed op bestaande informatie of services. Als gebruikers in het domein zich echter hebben aangemeld voor services waarvoor een licentie is vereist, wordt u gevraagd om licenties voor hen te kopen als onderdeel van het overnemen van de beheerdersrol. U kunt licenties kopen of verwijderen zodra het installatieproces voor beheerders is voltooid.
  
## <a name="related-articles"></a>Verwante artikelen

YouTube: [3 stappen voor het overnemen van it-beheerders voor Power BI en Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Overname van beheerders in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Selfservice-aanmelding gebruiken in uw organisatie](self-service-sign-up.md)
  
[Meer informatie over de rol van power bi-servicebeheerder](/power-bi/service-admin-role)